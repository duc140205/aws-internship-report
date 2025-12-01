---
title: "Blog 2"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Savings Plans: Cách triển khai chiến lược phân bổ chi phí (Chargeback) hiệu quả

Tác giả:  Alonso de Cosio and Ketan Kumar | Ngày: 28 THÁNG 2, 2025 | trong [Amazon Athena](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/category/analytics/amazon-athena/), [AWS Cloud Financial Management](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/category/aws-cloud-financial-management/), [AWS Cost and Usage Report](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/category/aws-cloud-financial-management/aws-cost-and-usage-report/), [Best Practices](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/category/post-types/best-practices/), [Technical How-to](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/category/post-types/technical-how-to/) | [Permalink](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/aws-savings-plans-how-to-implement-an-effective-chargeback-strategy/) | [Share](https://aws.amazon.com/vi/blogs/aws-cloud-financial-management/aws-savings-plans-how-to-implement-an-effective-chargeback-strategy/)


Khi các tổ chức phát triển, việc quản lý hạ tầng cloud có thể trở nên ngày càng phức tạp, đòi hỏi các chiến lược tài chính nâng cao để đảm bảo tối ưu chi phí.  [AWS Savings Plans](https://aws.amazon.com/vi/savingsplans/) cung cấp một mô hình định giá linh hoạt, mang lại khoản tiết kiệm đáng kể cho các dịch vụ AWS để đổi lại một cam kết về lượng sử dụng nhất quán, tính theo USD mỗi giờ, trong kỳ hạn một hoặc ba năm. Trong nhiều trường hợp, nhiều Savings Plans được áp dụng, bởi các nhóm riêng lẻ trực tiếp cam kết hoặc do các nhóm **FinOps** ưu tiên cho một số tài khoản cụ thể. Mặc dù các chiến lược này có thể mang lại khoản tiết kiệm lớn, nhưng chúng cũng làm tăng độ phức tạp trong việc đảm bảo quy trình chargeback công bằng và hiệu quả.

Trong bài viết này, chúng tôi sẽ chỉ cho bạn cách định nghĩa một cơ chế chargeback để phân bổ Savings Plans được mua trong **management account**, **linked accounts** hoặc cả hai cho các account nhận được Savings Plan discounts. Bạn có thể xác định account nào nhận được **Savings Plan discounts** và số tiền cần chargeback cho chúng dựa trên mức sử dụng cụ thể.

## Tìm hiểu về Savings Plans Discount Sharing
AWS cho phép khách hàng [chia sẻ khoản giảm giá (discount) của Savings Plan giữa các tài khoản](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ri-turn-off.html) thuộc cùng một [AWS Organization](https://aws.amazon.com/organizations/). Phí cam kết theo giờ của Savings Plan được tính cho account đã thực hiện giao dịch mua, tuy nhiên khi tính năng chia sẻ (sharing) được bật, các khoản giảm giá có thể áp dụng cho nhiều tài khoản trong tổ chức. Savings Plan discounts trước tiên được áp dụng cho tất cả các mức sử dụng đủ điều kiện trong tài khoản đã mua Savings Plan. Nếu có cam kết dư thừa mà không có mức sử dụng theo yêu cầu đủ điều kiện, thì cam kết chưa sử dụng đó sẽ được các tài khoản liên kết khác trong AWS Organization tận dụng.

Mặc dù [sharing giúp tối đa hóa khoản tiết kiệm](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html#calc-bills-sp), nó có thể đòi hỏi nỗ lực bổ sung để phân bổ lợi ích được chia sẻ một cách hợp lý trong toàn tổ chức Các tài khoản hưởng lợi từ ưu đãi của Savings Plan không có trách nhiệm thanh toán phí cam kết Savings Plan. Kết quả là, account chịu chi phí cam kết có thể không phải là người thụ hưởng duy nhất được hưởng lợi từ khoản tiết kiệm. Lợi ích được chia sẻ này đòi hỏi sự phân bổ chi phí cẩn trọng để đảm bảo các account bị charge một cách công bằng dựa trên mức độ sử dụng thực tế của Savings Plan.

Bây giờ chúng ta đã hiểu cách Savings Plans hoạt động và cách việc sharing ảnh hưởng đến chúng, hãy cùng tìm hiểu một chiến lược chargeback bằng cách sử dụng dữ liệu từ [Cost and Usage Report (CUR) 2.0](https://docs.aws.amazon.com/cur/latest/userguide/table-dictionary-cur2.html).


## Điều kiện tiên quyết
Tạo một  [AWS Data Export](https://aws.amazon.com/aws-cost-management/aws-data-exports/) với CUR 2.0 và cấu hình  [AWS Glue](https://aws.amazon.com/glue/) để lập danh mục dữ liệu. Điều này cho phép bạn sử dụng [Amazon Athena](https://aws.amazon.com/athena/) để chạy các truy vấn và phân tích dữ liệu CUR 2.0. Để thực hiện điều này, bạn cần làm như sau:

**1. Cấu hình CUR 2.0 với AWS Data Export:**
1. Đăng nhập vào  [AWS Management console](https://aws.amazon.com/console/)
2. Điều hướng đến AWS Billing and Cost Management. Chọn Data Export và nhấp vào Create để bắt đầu thiết lập export của bạn.
  
 ![Hình 1 - Tạo Data Exports](/images/3-BlogsTranslated/3.2-Blog2/1.png)
 <p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 1 - Tạo Data Exports</em></p>
3. Chọn <b>Standard data export</b>, đặt tên cho export của bạn và chọn <b>CUR 2.0</b> làm loại bảng dữ liệu.
  
 ![Hình 2 - Cấu hình export](/images/3-BlogsTranslated/3.2-Blog2/2.png)
 <p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 2 - Cấu hình export</em></p>

4. Việc bật <b>Include resource IDs</b> và <b>Split cost allocation data</b> là tùy chọn
5. Chọn Time granularity là <b>Hourly</b>
6. Đặt <b>Parquet</b> làm định dạng nén, và chọn <b>Overwrite existing data export file</b> cho versioning.

![Hình 3 - Cấu hình các tùy chọn phân phối export](/images/3-BlogsTranslated/3.2-Blog2/3.png)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 3 - Cấu hình các tùy chọn phân phối export</em></p>

7. Chỉ định Amazon S3 bucket đích và path prefix nơi dữ liệu CUR 2.0 sẽ được lưu trữ.
8. Hoàn tất thiết lập bằng cách chọn <b>Create</b>.

**2. Cấu hình AWS Glue để truy vấn Dữ liệu CUR**
1. Điều hướng đến console của <b>AWS Glue</b> và chọn <b>Data Catalog > Crawlers</b> để bắt đầu quá trình lập danh mục dữ liệu CUR 2.0.
2. Nhấp vào <b>Create Crawler</b> và gán một tên crawler duy nhất.

![Hình 4 - Tạo AWS Glue Crawler](/images/3-BlogsTranslated/3.2-Blog2/4.png)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 4 - Tạo AWS Glue Crawler</em></p>

3. Đối với câu hỏi <b>Is your data already mapped to Glue tables?</b> chọn Not yet
4. Nhấp vào Add a data source, chọn S3 và chỉ định vị trí Amazon S3 từ bước cấu hình S3 ở phần 1, nơi dữ liệu CUR 2.0 của bạn được export, sử dụng định dạng: Đối với câu hỏi Is your data already mapped to Glue tables? chọn Not yet
Nhấp vào Add a data source, chọn S3 và chỉ định vị trí Amazon S3 từ bước cấu hình S3 ở phần 1, nơi dữ liệu CUR 2.0 của bạn được export, sử dụng định dạng: `s3://<bucket-name>/<prefix>/<export-name>/data/`

![Hình 5 - Tạo nguồn dữ liệu S3 để crawler dữ liệu CUR](/images/3-BlogsTranslated/3.2-Blog2/5.png)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 5 - Tạo nguồn dữ liệu S3 để crawler dữ liệu CUR</em></p>

5. Nhấp vào <b>Add an S3 data source</b> và sau đó nhấp vào <b>Next</b>
6. Nhấp vào <b>Create new IAM role</b>, thao tác này sẽ tạo vai trò AWS Glue mới thay cho bạn. Vai trò này cho phép Glue truy cập vào bucket S3 nơi các tệp CUR2.0 được lưu trữ.
7. Tạo một target database bằng cách nhấp vào <b>Add database</b>. Nhập tên database và nhấp vào <b>Create database</b>
8. Quay lại console AWS Glue và chọn database đã tạo ở bước trước. Đặt crawler schedule thành <b>On demand</b> để chỉ chạy khi cần thiết.
9. Xác nhận các cài đặt của bạn và chọn <b>Create Crawler</b>.
10. Khi crawler đã sẵn sàng, hãy chọn nó và nhấp vào <b>Run</b>. Thao tác này sẽ xử lý và lập danh mục dữ liệu, tạo ra các bảng có thể truy cập được bởi Amazon Athena.


## Sử dụng CUR 2.0 cho việc chargeback Savings Plans
Sau khi các điều kiện tiên quyết trên được cấu hình, hãy sử dụng query sau để xác định các tài khoản liên kết đã nhận được Savings Plan discounts. Cột Effective Cost cung cấp chi phí tương ứng với số tiền cam kết Savings Plan đã được các tài khoản liên kết sử dụng. Đây sẽ là số tiền bạn sẽ sử dụng để chargeback cho từng tài khoản liên kết.

1. Điều hướng đến console của <b>Amazon Athena</b> để chạy một query. Xem lại [chi tiết](https://docs.aws.amazon.com/cur/latest/userguide/cur-ate-run.html) về cách chạy SQL queries trong Athena.
2. Sao chép query dưới đây vào trình soạn thảo Query của bạn. Đảm bảo cập nhật <b>Table Name</b> trong query.

```sql
select
    DATE_FORMAT(bill_billing_period_start_date, '%Y-%m-%d') as "Date",
    line_item_usage_account_id as "Account Id",
    savings_plan_offering_type as "Savings Plan Type",
    split_part(savings_plan_savings_plan_a_r_n, '/', 2) AS "Saving Plan ID",
    savings_plan_payment_option as "Savings Plan Payment Option",
    line_item_line_item_type as "Item Type",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_recurring_commitment_for_billing_period
        end
    ) + sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_amortized_upfront_commitment_for_billing_period
        end
    ) as "Savings Plan Fee",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_recurring_commitment_for_billing_period
        end
    ) + sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_amortized_upfront_commitment_for_billing_period
        end
    ) - sum(savings_plan_used_commitment) as "Unused commitment",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanRecurringFee' then 0
            else savings_plan_savings_plan_effective_cost
        end
    ) as "Effective Cost",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanRecurringFee' then 0
            else line_item_unblended_cost
        end
    ) - sum(
        case
            when line_item_line_item_type = 'SavingsPlanRecurringFee' then 0
            else savings_plan_savings_plan_effective_cost
        end
    ) - (
        sum(
            case
                when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
                else savings_plan_recurring_commitment_for_billing_period
            end
        ) + sum(
            case
                when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
                else savings_plan_amortized_upfront_commitment_for_billing_period
            end
        ) - sum(savings_plan_used_commitment)
    ) as "Savings"
from
    <Table Name>
where
    line_item_line_item_type in ('SavingsPlanCoveredUsage', 'SavingsPlanRecurringFee')
    and bill_billing_period_start_date = DATE_TRUNC('month', CURRENT_DATE) - INTERVAL '1' month
group by
    bill_billing_period_start_date,
    line_item_usage_account_id,
    savings_plan_offering_type,
    savings_plan_savings_plan_a_r_n,
    savings_plan_payment_option,
    line_item_line_item_type
order by
    sum(savings_plan_savings_plan_effective_cost) desc;
```

Để hiểu rõ hơn, hãy phân tích hai thành phần quan trọng có trong AWS CUR 2.0:

- **SavingsPlanRecurringFee**: Đây là field trong output nơi <span style="color:red;">Item Type = 'SavingsPlanRecurringFee'</span>. Nó đại diện cho chi phí mà account mua có nghĩa vụ phải trả cho cam kết Savings Plan. Đây là một chi phí cố định, bất kể toàn bộ cam kết có được sử dụng hay không. Tùy thuộc vào loại Savings Plan, số tiền này có thể được phản ánh dưới dạng unblended hoặc amortized.

- **SavingsPlanCoveredUsage**: Đây là field trong output nơi <span style="color:red;">Item Type = 'SavingsPlanCoveredUsage'</span>. Nó đại diện cho việc sử dụng thực tế của Savings Plan, cho thấy bao nhiêu phần của Savings Plan đã cam kết được áp dụng cho việc sử dụng trong toàn tổ chức. Việc sử dụng này có thể được phân bổ trên nhiều account, tùy thuộc vào cấu trúc và sự phân bổ workload của tổ chức.

Để thực hiện chargeback cho Savings Plan, điều quan trọng là phải sử dụng cột **Effective Cost** được liên kết với mỗi linked account. Cột này cung cấp chi phí tương ứng với phần cam kết Savings Plan đã được mỗi linked account sử dụng. Mục tiêu là đảm bảo rằng mỗi linked account nhận được một khoản phí Savings Plan tương ứng với lợi ích mà nó đã nhận được từ Savings Plan.

Cũng rất quan trọng để xác thực cột **Unused Commitment** cho các hàng có <span style="color:red;">SavingsPlanRecurringFee</span>. Nếu giá trị trong cột này lớn hơn 0$, điều đó cho thấy Savings Plan không được sử dụng hết. Mặc dù việc sử dụng dưới mức này có thể chỉ ra khả năng mất đi một phần khoản tiết kiệm, nhưng điều quan trọng là phải xác thực. Các tổ chức có thể cố ý mua các cam kết Savings Plan vượt quá một chút so với mức sử dụng dự kiến, vì tổng khoản tiết kiệm từ discount vẫn có thể lớn hơn chi phí của phần không sử dụng, mang lại lợi ích tiết kiệm ròng cho tổ chức.

## Ví dụ <br>
Trong bảng dưới đây, Savings Plan Type là <span style="color:red;">No Upfront</span>. Phí định kỳ hàng tháng được tính cho Account ID A vì chúng ta thấy trường ‘SavingsPlanRecurringFee’ tương ứng. Mức sử dụng đủ điều kiện trong Account ID A sẽ nhận được discount trước vì đây là tài khoản mua Savings Plan. Trong tổng số cam kết hàng tháng là $12,410.68, $8,363.12 là chi phí hiệu dụng (effective cost) sẽ được chargeback cho Account ID A. Account B đã sử dụng $1,361.26 trong tổng cam kết định kỳ, đây sẽ là giá trị chargeback của Account B. Chúng ta cũng có thể quan sát thấy rằng cam kết không sử dụng là $0 và tổng chi phí hiệu dụng khớp với phí định kỳ, điều này cho thấy Savings Plan được sử dụng hết.

![Hình 6 - Báo cáo ví dụ cho thấy sự phân bổ lợi ích của savings plans giữa các tài khoản](/images/3-BlogsTranslated/3.2-Blog2/6.jpg)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 6 - Báo cáo ví dụ cho thấy sự phân bổ lợi ích của savings plans giữa các tài khoản</em></p>

Hãy xem một ví dụ khác:

Trong bảng dưới đây, chúng ta quan sát thấy Savings Plan Type là <span style="color:red;">All Upfront</span>, tương ứng với phần khấu hao (amortized portion) của khoản thanh toán trả trước cho kỳ thanh toán. Dữ liệu cho thấy Savings Plan đã được mua trong Account ID A và được Account ID A sử dụng hết, vì ‘Unused Commitment’ là $0. Trong trường hợp này, vì chỉ có một tài khoản được hưởng lợi từ Savings Plan và phí định kỳ khớp với chi phí hiệu dụng.

![Hình 7 - Báo cáo ví dụ cho thấy việc tiêu thụ lợi ích của savings plans bởi tài khoản mua](/images/3-BlogsTranslated/3.2-Blog2/7.jpg)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Hình 7 - Báo cáo ví dụ cho thấy việc tiêu thụ lợi ích của savings plans bởi tài khoản mua</em></p>

## Kết luận
Trong bài viết này, chúng tôi đã thảo luận về tác động của việc sharing Savings Plan đối với việc sử dụng nó. Khi tính năng sharing được bật, có thể có những account nhận được lợi ích từ Savings Plan discounts mà không phải trả phí Savings Plan. Account thực hiện giao dịch mua là bên duy nhất có nghĩa vụ thanh toán phí Savings Plan.

Chúng tôi đã sử dụng một query có chủ đích trong AWS Cost and Usage report 2.0 để thiết kế một cơ chế chargeback cho phép chúng tôi xác định tất cả những người hưởng lợi từ Savings Plan discounts và tỷ lệ phí định kỳ mà họ có thể bị tính. Sử dụng chiến lược này, giờ đây bạn có thể sử dụng các cơ chế chargeback nội bộ của công ty để tính phí lại (chargeback) cho các tài khoản một cách chính xác dựa trên mức sử dụng và khoản tiết kiệm mà họ nhận được, thay vì chỉ tính phí cho account nắm giữ Savings Plan. Phương pháp này cho phép phân phối công bằng và minh bạch cả chi phí và lợi ích của Savings Plans, giúp điều chỉnh trách nhiệm tài chính với việc sử dụng thực tế.

Chiến lược này thúc đẩy sự minh bạch, trách nhiệm và khuyến khích việc sử dụng cloud một cách có ý thức giữa các team. Bằng cách đảm bảo rằng tất cả các account được tính phí theo lợi ích Savings Plan mà họ nhận được, bạn sẽ thúc đẩy một văn hóa ý thức về chi phí trong tổ chức của mình.

TAGS: [Chargeback](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/chargeback/), [Cost Allocation](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/cost-allocation/), [Savings Plans](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/savings-plans/), [Showback](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/showback/)


<table>
    <tr>
        <td style="vertical-align:top; width:110px; text-align:center;">
            <img src="/images/3-BlogsTranslated/3.2-Blog2/alonso.jpg" alt="Alonso de Cosio" style="width:100px; border-radius:8px; display:block; margin:0 auto 8px auto;"/>
            <div style="font-weight:bold; margin-top:4px;">Alonso de Cosio</div>
        </td>
        <td style="vertical-align:top; padding-left:20px;">
            Alonso de Cosio là <b>Principal Technical Account Manager</b> tại <b>AWS</b>. Trong vai trò của mình, anh cung cấp tư vấn và hướng dẫn kỹ thuật chiến lược để giúp khách hàng lập kế hoạch và xây dựng các giải pháp bằng cách sử dụng AWS best practices. Anh đam mê việc xây dựng các hệ thống doanh nghiệp có tính mô-đun và khả năng mở rộng trên AWS bằng cách sử dụng các công nghệ <b>serverless</b>. Ngoài công việc, Alonso thích dành thời gian cho vợ và chú chó của mình, cũng như đi biển và du lịch.
        </td>
    </tr>
</table>

<table>
    <tr>
        <td style="vertical-align:top; width:110px; text-align:center;">
            <img src="/images/3-BlogsTranslated/3.2-Blog2/ketan.jpg" alt="Ketan Kumar" style="width:100px; border-radius:8px; display:block; margin:0 auto 8px auto;"/>
            <div style="font-weight:bold; margin-top:4px;">Ketan Kumar</div>
        </td>
        <td style="vertical-align:top; padding-left:20px;">
            Ketan là <b>Senior Technical Account Manager</b> tại <b>AWS</b>, làm việc tại <b>Dublin, Ireland</b>. Trong vai trò của mình, anh cung cấp hướng dẫn kỹ thuật chiến lược giúp khách hàng sử dụng AWS best practices để lập kế hoạch và xây dựng các giải pháp. Anh tận tâm hỗ trợ khách hàng phát triển các kiến trúc có khả năng mở rộng, linh hoạt và tiết kiệm chi phí.<br/>
            Trong thời gian rảnh, Ketan thích dành thời gian cho vợ và gia đình, đi du lịch, chơi game và xem phim.
        </td>
    </tr>
</table>



