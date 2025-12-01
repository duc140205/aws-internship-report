---
title: "Blog 3"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Weekly Roundup: Giảm giá Amazon S3 Express One Zone, Pixtral Large trên Amazon Bedrock, Amazon Nova Sonic và nhiều hơn nữa (14 tháng 4, 2025)

Tác giả: Elizabeth Fuentes | Ngày: 14 THÁNG 04 2025 |  trong [Amazon Aurora](https://aws.amazon.com/blogs/aws/category/database/amazon-aurora/), [Amazon Bedrock](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/), [Amazon Bedrock Agents](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-agents/), [Amazon Bedrock Guardrails](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-guardrails/), [Amazon Bedrock Prompt Management](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-prompt-management/), [Amazon CloudWatch](https://aws.amazon.com/blogs/aws/category/management-tools/amazon-cloudwatch/), [Amazon Nova](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-nova/), [Amazon Personalize](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-personalize/), [Amazon SageMaker](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/sagemaker/), [Announcements](https://aws.amazon.com/blogs/aws/category/post-types/announcements/), [AWS Step Functions](https://aws.amazon.com/blogs/aws/category/application-services/aws-step-functions/), [Launch](https://aws.amazon.com/blogs/aws/category/news/launch/), [News](https://aws.amazon.com/blogs/aws/category/news/), [Storage](https://aws.amazon.com/blogs/aws/category/storage/)


Mùa sự kiện [Amazon Web Services (AWS) Summit 2025](https://aws.amazon.com/events/summits/) đã khởi động trong tuần này, bắt đầu với [Paris Summit](https://aws.amazon.com/events/summits/paris/). Những sự kiện miễn phí này quy tụ cộng đồng điện toán đám mây toàn cầu để học hỏi và hợp tác. [AWS Community Day Romania](https://www.google.com/search?q=https://romania.awscommunity.dev/), được tổ chức vào ngày 11 tháng 4, đã cho thấy cách cộng đồng địa phương tạo ra cơ hội cho sự phát triển và hòa nhập tập thể.

![Hình ảnh từ AWS Summit Paris 2025](/images/3-BlogsTranslated/3.3-Blog3/1.png)

<u><b>Những tính năng được ra mắt trong tuần trước</b></u>

[Công bố giảm giá tới 85% cho Amazon S3 Express One Zone — S3 Express One Zone](https://aws.amazon.com/es/blogs/aws/up-to-85-price-reductions-for-amazon-s3-express-one-zone/), một lớp lưu trữ hiệu năng cao, hiện đã giảm giá lưu trữ 31%, giá yêu cầu (request) PUT 55% và giá yêu cầu GET 85% Ngoài ra, S3 Express One Zone đã giảm 60% phí trên mỗi GB cho việc tải lên và truy xuất dữ liệu. Các khoản phí này hiện áp dụng cho tất cả các byte được truyền thay vì chỉ các phần của yêu cầu lớn hơn 512 KB. Đây là bảng giảm giá tại Khu vực AWS US East (N. Virginia):

| Giá                                   | Giá trước đây                              | Giá mới                        | Mức giảm giá |
|----------------------------------------|--------------------------------------------|-------------------------------|--------------|
| **Storage**<br/>(per GB-Month)         | $0.16                                      | $0.11                         | 31%          |
| **Writes**<br/>(PUT requests)          | $0.0025 mỗi 1.000 request tối đa 512 KB    | $0.00113 mỗi 1.000 request    | 55%          |
| **Reads**<br/>(GET requests)           | $0.0002 mỗi 1.000 request tối đa 512 KB    | $0.00003 mỗi 1.000 request    | 85%          |
| **Data upload**<br/>(per GB)           | $0.008                                     | $0.0032                       | 60%          |
| **Truy xuất dữ liệu**<br/>(per GB)     | $0.0015                                    | $0.0006                       | 60%          |


[AWS công bố mô hình Pixtral Large 25.02 trong Amazon Bedrock dạng phi máy chủ (serverless) — Pixtral Large 25.02](https://aws.amazon.com/vi/blogs/aws/aws-announces-pixtral-large-25-02-model-in-amazon-bedrock-serverless/), được phát triển bởi [Mistral AI](https://mistral.ai/), kết hợp khả năng hiểu ngôn ngữ và thị giác tiên tiến, tự hào với cửa sổ ngữ cảnh 128K và khả năng đa ngôn ngữ. Thiết kế tập trung vào tác nhân (agent) này giúp đơn giản hóa việc tích hợp với các hệ thống hiện có. Việc tuân thủ  [câu lệnh (prompt)](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) cải thiện độ tin cậy khi làm việc với các ứng dụng [Retrieval Augmented Generation (RAG)](https://aws.amazon.com/what-is/retrieval-augmented-generation/?trk=4b29643c-e00f-4ab6-ab9c-b1fb47aa1708&sc_channel=blog) và các kịch bản có ngữ cảnh lớn.

![](/images/3-BlogsTranslated/3.3-Blog3/2.png)

[Giới thiệu Amazon Nova Sonic: Cuộc trò chuyện bằng giọng nói giống như người thật cho các ứng dụng AI tạo sinh — Amazon Nova Sonic](https://aws.amazon.com/vi/blogs/aws/introducing-amazon-nova-sonic-human-like-voice-conversations-for-generative-ai-applications/), thành viên mới nhất trong [dòng mô hình nền tảng (foundation models - FMs) Amazon Nova, đã có mặt trong Amazon Bedrock](https://aws.amazon.com/nova/) để tạo ra các cuộc trò chuyện bằng giọng nói giống như người thật cho các ứng dụng. Nó hợp nhất việc xử lý giọng nói và văn bản vào một mô hình duy nhất, giảm độ phức tạp và tăng cường tương tác tự nhiên. Bắt đầu ngay hôm nay với [Amazon Nova model cookbook repository.](https://github.com/aws-samples/amazon-nova-samples)

<video style="width:100%;" controls>
  <source src="/images/3-BlogsTranslated/3.3-Blog3/Nova-s2s-blog.mp4" type="video/mp4">
</video>

[Amazon Bedrock Guardrails tăng cường an toàn cho ứng dụng AI tạo sinh với các khả năng mới](https://aws.amazon.com/vi/blogs/aws/amazon-bedrock-guardrails-enhances-generative-ai-application-safety-with-new-capabilities/) — [Amazon Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/) giới thiệu các khả năng mới để tăng cường an toàn cho ứng dụng AI tạo sinh, bao gồm phát hiện nội dung độc hại (toxicity) đa phương thức, bảo vệ Thông tin nhận dạng cá nhân (PII) nâng cao, thực thi chính sách [AWS Identity and Access Management (AWS IAM)](https://aws.amazon.com/iam/), áp dụng guardrail có chọn lọc và chế độ giám sát để phân tích trước khi triển khai.


[AWS App Studio giới thiệu danh mục giải pháp dựng sẵn và tính năng Import và Export giữa các instance](https://aws.amazon.com/vi/about-aws/whats-new/2025/04/aws-app-studio-prebuilt-solutions-catalog-import-export/) — Đây là một danh mục giải pháp dựng sẵn với các ứng dụng và mẫu sẵn sàng sử dụng cùng chức năng Import và Export giữa các instance. Các tính năng này giúp bạn tối ưu quy trình phát triển ứng dụng, giảm thời gian thiết lập xuống dưới 15 phút. Tìm hiểu thêm về điều này trong bài blog [AWS App Studio giới thiệu danh mục giải pháp dựng sẵn và tính năng Import và Export giữa các instance.](https://aws.amazon.com/vi/blogs/machine-learning/aws-app-studio-introduces-a-prebuilt-solutions-catalog-and-cross-instance-import-and-export/)


[Amazon Nova Reel 1.1: Hỗ trợ video đa cảnh quay lên đến 2 phút](https://aws.amazon.com/es/blogs/aws/amazon-nova-reel-1-1-featuring-up-to-2-minutes-multi-shot-videos/) — [Amazon Nova Reel](https://aws.amazon.com/nova/) 1.1 nâng cao khả năng tạo video thông qua [Amazon Bedrock](https://aws.amazon.com/bedrock/) với sự hỗ trợ cho các video đa cảnh quay dài 2 phút. Bây giờ bạn có thể tạo nội dung bằng cách sử dụng prompt đơn để tạo tự động hoặc prompt tùy chỉnh cho từng cảnh quay riêng lẻ, mang lại các tùy chọn linh hoạt cho việc tạo nội dung marketing và mạng xã hội.


<video style="width:100%;" controls>
  <source src="/images/3-BlogsTranslated/3.3-Blog3/awsnews-1526_Underwater Racoon.mp4" type="video/mp4">
</video>


[AWS IAM Identity Center hiện cung cấp thông báo lỗi chi tiết hơn và ghi log AWS CloudTrail cho các vấn đề cấp phát (provisioning)](https://aws.amazon.com/vi/about-aws/whats-new/2025/02/aws-iam-identity-center-error-messages-cloudtrail-logging-provisioning-issues/) — [AWS Identity and Access Management (IAM) Identity Center](https://aws.amazon.com/iam/identity-center/) đã cải tiến dịch vụ của mình với các thông báo lỗi chi tiết hơn và khả năng ghi log qua [AWS CloudTrail.](https://aws.amazon.com/cloudtrail/) Các cập nhật này giúp người dùng xử lý sự cố đồng bộ hóa tốt hơn khi quản lý danh tính nhân viên trên các [tài khoản AWS](https://aws.amazon.com/organizations/getting-started/best-practices/) và ứng dụng, đồng thời cho phép giám sát và kiểm tra tự động các vấn đề cấp phát (provisioning).


[Bảng điều khiển AWS WAF bổ sung các biểu đồ trực quan hóa top insights mới tại các khu vực bổ sung](https://aws.amazon.com/vi/about-aws/whats-new/2025/02/aws-waf-console-top-insights-visualizations-additional-regions/) — Bảng điều khiển [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) hiện cung cấp các tính năng trực quan hóa lưu lượng truy cập nâng cao tại [AWS GovCloud (US) Regions.](https://aws.amazon.com/govcloud-us/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) Bảng điều khiển lưu lượng (traffic dashboard) mới bao gồm top insights dựa trên log từ [Amazon CloudWatch](https://aws.amazon.com/vi/cloudwatch/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog), giúp khách hàng phân tích các mẫu lưu lượng truy cập, xác định các mối đe dọa bảo mật và tối ưu hóa cấu hình WAF thông qua các số liệu chi tiết.



[AWS Step Functions mở rộng các tùy chọn nguồn dữ liệu và đầu ra cho Distributed Map](https://aws.amazon.com/vi/about-aws/whats-new/2025/02/aws-step-functions-data-source-output-option-distributed-map/) — [AWS Step Functions](https://aws.amazon.com/step-functions/) cải tiến Distributed Map với hỗ trợ nguồn dữ liệu mở rộng, bao gồm JSONL và các định dạng tệp được phân tách khác nhau từ [Amazon Simple Storage Service (Amazon S3).](https://aws.amazon.com/s3/) Bản cập nhật cũng bổ sung các tùy chọn chuyển đổi đầu ra mới, cho phép các quy trình xử lý song song linh hoạt hơn và tích hợp tốt hơn với các hệ thống hạ nguồn.


[Amazon CloudWatch hiện cung cấp chẩn đoán tranh chấp khóa (lock contention) cho Aurora PostgreSQL](https://aws.amazon.com/vi/about-aws/whats-new/2025/02/amazon-cloudwatch-lock-contention-diagnostics-aurora-postgresql/) — [Amazon CloudWatch Database Insights](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Database-Insights.html?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) giới thiệu tính năng chẩn đoán lock contention cho [Amazon Aurora PostgreSQL](https://aws.amazon.com/rds/aurora/postgresql-features/) ở chế độ Advanced. Tính năng này trực quan hóa các **phiên (session)** đang chặn và đang chờ, giúp người dùng xác định nguyên nhân gốc rễ của các vấn đề lock contention, với khả năng lưu trữ dữ liệu lịch sử trong 15 tháng để khắc phục sự cố toàn diện.
Cập nhật tất cả các thông báo của AWS trên trang [What’s New with AWS?.](https://aws.amazon.com/new/)

<b><u>Các bài đăng blog khác của AWS</u></b>

[**Reduce ML training costs with Amazon SageMaker HyperPod**](https://aws.amazon.com/vi/blogs/machine-learning/reduce-ml-training-costs-with-amazon-sagemaker-hyperpod/) — [Amazon SageMaker HyperPod](https://aws.amazon.com/sagemaker/hyperpod/) giải quyết các lỗi phần cứng trong quá trình huấn luyện mô hình [Machine Learning (ML)](https://aws.amazon.com/what-is/machine-learning/) quy mô lớn bằng cách tự động phát hiện và thay thế các máy chủ (instance) bị lỗi. Giải pháp này giảm thời gian gián đoạn (downtime) từ 280 xuống còn 40 phút cho mỗi lần fail, có khả năng tiết kiệm 32% thời gian huấn luyện cho các cụm lớn. Đối với một công việc huấn luyện 10 triệu giờ GPU, điều này tương đương $25,6 triệu chi phí tiết kiệm.


[**Model customization, RAG, or both: A case study with Amazon Nova**](https://aws.amazon.com/vi/blogs/machine-learning/model-customization-rag-or-both-a-case-study-with-amazon-nova/) — Một nghiên cứu so sánh tùy chỉnh mô hình với các phương pháp fine-tuning và [Retrieval Augmented Generation (RAG)](https://aws.amazon.com/what-is/retrieval-augmented-generation/) với các [Amazon Nova models.](https://aws.amazon.com/ai/generative-ai/nova/) Các kết quả chính cho thấy việc kết hợp cả hai phương pháp mang lại kết quả tốt nhất: RAG hoạt động tốt cho dữ liệu động và hiểu biết theo miền, trong khi fine-tuning vượt trội trong các tác vụ chuyên biệt và giảm độ trễ.


[**Generate user-personalized communication with Amazon Personalize and Amazon Bedrock**](https://aws.amazon.com/blogs/machine-learning/generate-user-personalized-communication-with-amazon-personalize-and-amazon-bedrock/) — [Amazon Personalize](https://aws.amazon.com/personalize/) và Amazon Bedrock hợp tác để tạo ra các email marketing được cá nhân hóa. Tìm hiểu cách tạo các thông điệp cá nhân hóa cho người dùng bằng cách kết hợp Amazon Personalize để đề xuất phim với Amazon Bedrock để tạo nội dung email phù hợp dựa trên sở thích và đặc điểm người dùng.

![](/images/3-BlogsTranslated/3.3-Blog3/3.png)

[**Implement human-in-the-loop confirmation with Amazon Bedrock Agents**](https://aws.amazon.com/vi/blogs/machine-learning/implement-human-in-the-loop-confirmation-with-amazon-bedrock-agents/) — Khi triển khai xác thực của con người trong [Amazon Bedrock Agents](https://aws.amazon.com/bedrock/agents/), các nhà phát triển có hai framework chính để sử dụng: xác nhận của người dùng (user confirmation) và trả lại quyền kiểm soát (return of control - ROC). Ví dụ với ứng dụng HR, user confirmation cho phép xác thực yes/no đơn giản trước khi thực hiện hành động, trong khi ROC cho phép người dùng sửa đổi các tham số trước khi thực thi.


[**Multi-LLM routing strategies for generative AI applications on AWS**](https://aws.amazon.com/blogs/machine-learning/multi-llm-routing-strategies-for-generative-ai-applications-on-aws/) — Tìm hiểu cách triển khai các chiến lược định tuyến đa-[Large Language Model (LLM)](https://aws.amazon.com/what-is/large-language-model/) cho các ứng dụng [AI tạo sinh](https://aws.amazon.com/what-is/generative-ai/) của AWS bằng cách sử dụng định tuyến tĩnh, định tuyến động với Amazon Bedrock, hoặc các giải pháp tùy chỉnh để chọn mô hình tối ưu và cân bằng chi phí.

![](/images/3-BlogsTranslated/3.3-Blog3/4.png)

Đây là các bài đăng yêu thích của cá nhân tôi từ [<u>community.aws</u>](https://builder.aws.com/):

[Building a RAG System for Video Content Search and Analysis](https://builder.aws.com/content/2stievBb8ZuQtebTPNm8kC7ul0c/building-a-rag-system-for-video-content-search-and-analysis?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — Trong blog này, tôi sẽ chỉ cho bạn cách xây dựng một hệ thống RAG giúp nội dung video có thể tìm kiếm và phân tích được. Việc khai thác nội dung video chưa bao giờ quan trọng hơn trong bối cảnh kỹ thuật số ngày nay. Cho dù bạn đang quản lý tài liệu giáo dục, đào tạo doanh nghiệp hay nội dung giải trí, khả năng tìm kiếm và phân tích nội dung video một cách hiệu quả có thể thay đổi cách chúng ta tương tác với các tài nguyên đa phương tiện.


[Build Serverless GenAI Apps Faster with Amazon Q Developer CLI Agent](https://builder.aws.com/content/2uVl543Irg1pNRSkGY4yvth7Tmw/build-serverless-genai-apps-faster-with-amazon-q-developer-cli-agent?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — [Amazon Q Developer](https://aws.amazon.com/q/) CLI Agent cho phép phát triển ứng dụng GenAI serverless nhanh chóng. Với một prompt, nó tạo ra mã cơ sở hạ tầng, các hàm Lambda và tích hợp với Claude 3 Haiku trên Amazon Bedrock.

[Speech-to-Speech AI: From Dr. Sbaitso to Amazon Nova Sonic](http://community.aws/content/2vEZph0MzNXYJJSrNkgN9V2kYLY/speech-to-speech-ai-from-dr-sbaitso-to-amazon-nova-sonic?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — Sự phát triển của speech-to-speech AI, từ Dr. Sbaitso (những năm 1990) đến Amazon Nova Sonic. Dịch vụ mới cho phép hội thoại hai chiều thời gian thực qua Amazon Bedrock, mang lại trải nghiệm tự nhiên hơn cho ứng dụng.

[Setup Model Context Protocol (MCP) using Amazon Bedrock](https://builder.aws.com/content/2vPB0cvCY08EWYleQ8vcMCOvQVg/run-local-mcp-desktop-client-using-amazon-bedrock?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — Hướng dẫn thiết lập client MCP (Model Context Protocol) trên desktop để làm việc với các mô hình Amazon Bedrock, cho phép tích hợp liền mạch giữa ứng dụng AI và các công cụ bên ngoài thông qua client Goose.

<b><u>Các sự kiện sắp tới của AWS</u></b>

Kiểm tra lịch của bạn và đăng ký các sự kiện AWS sắp tới sau:

[AWS GenAI Lofts — GenAI Lofts](https://aws.amazon.com/startups/lp/aws-gen-ai-lofts?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) có mặt trên khắp thế giới, cung cấp không gian hợp tác và trải nghiệm chuyên sâu (immersive) cho các công ty khởi nghiệp và nhà phát triển. Bạn có thể tham gia các sự kiện [GenAI Loft San Francisco](https://aws.amazon.com/startups/events?tag=GENAI_LOFT_SAN_FRANCISCO) trực tiếp như [GenAI in EdTech: A Hands-On Workshop](https://aws.amazon.com/startups/events/genai-in-edtech-a-hands-on-workshop) (ngày 15 tháng 4), và [Unstructured Data Meetup SF](https://aws.amazon.com/startups/events/built-on-bedrock-demo-nights-sf-202504) (ngày 16 tháng 4). Tìm sự kiện gần bạn nhất tại [GenAI Lofts.](https://www.google.com/search?q=https://aws.amazon.com/events/genai-lofts/)

[AWS Summits](https://aws.amazon.com/vi/events/summits/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — Tham gia các sự kiện trực tuyến và trực tiếp miễn phí quy tụ cộng đồng điện toán đám mây để kết nối, hợp tác và tìm hiểu về AWS. Đăng ký tại thành phố gần bạn nhất: [Amsterdam](https://aws.amazon.com/events/summits/amsterdam/) (ngày 16 tháng 4), [London](https://aws.amazon.com/events/summits/london/) (ngày 30 tháng 4), và [Poland](https://aws.amazon.com/events/summits/poland/) (ngày 5 tháng 5).

[AWS re:Inforce](https://reinforce.awsevents.com/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — AWS re:Inforce (16–18 tháng 6) tại Philadelphia, PA, là sự kiện học tập hàng năm của chúng tôi dành cho mọi thứ liên quan đến bảo mật đám mây AWS. [Đăng ký đã mở](https://reinforce.awsevents.com/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog). Hãy sẵn sàng tham gia cùng hơn 5.000 chuyên gia và nhà lãnh đạo bảo mật.

[AWS Community Days](https://aws.amazon.com/vi/events/community-day/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) — Tham gia các hội nghị do cộng đồng tổ chức với các buổi thảo luận kỹ thuật, workshop và lab thực hành dẫn dắt bởi các chuyên gia AWS và người dùng trong ngành. [Community Days sắp tới](https://aws.amazon.com/vi/events/community-day/?trk=fccf147c-636d-45bf-bf0a-7ab087d5691a&sc_channel=blog) là 19 tháng 4 ở [Thổ Nhĩ Kỳ](https://aws.cloudturkey.io/), và 29 tháng 4 ở [Prague](https://awscommunityday.cz/2025/), với [Jeff Barr](https://www.linkedin.com/in/jeffbarr/) là diễn giả mở đầu.

Bạn có thể duyệt qua tất cả các [sự kiện trực tiếp và virtual events sắp tới.](https://aws.amazon.com/events)

Tạo [AWS Builder ID](https://profile.aws.amazon.com/) của bạn và đặt bí danh của bạn. Builder ID là một thông tin đăng nhập phổ quát cho phép bạn truy cập—ngoài AWS Management Console—vào các công cụ và tài nguyên của AWS, bao gồm hơn 600 khóa đào tạo miễn phí, các tính năng cộng đồng và các công cụ dành cho nhà phát triển như Amazon Q Developer.
Đó là tất cả cho tuần này. Hãy theo dõi Tổng hợp tin tức hàng tuần vào tuần tới!

— [Eli](https://www.linkedin.com/in/lizfue/)

<i>Cảm ơn Andra Somesan về bức ảnh của AWS Community Romania và Thembile Martis về bức ảnh của AWS Paris Summit.</i>

<i>Bài đăng này là một phần của series Weekly Roundup của chúng tôi. Hãy kiểm tra lại mỗi tuần để có một bản tóm tắt nhanh về các tin tức và thông báo thú vị từ AWS!</i>


<table>
    <tr>
        <td style="vertical-align:top; width:110px; text-align:center;">
            <img src="/images/3-BlogsTranslated/3.3-Blog3/elizabeth.jpeg" alt="Elizabeth Fuentes" style="width:100px; border-radius:8px; display:block; margin:0 auto 8px auto;"/>
            <div style="font-weight:bold; margin-top:4px;">Elizabeth Fuentes</div>
        </td>
        <td style="vertical-align:top; padding-left:20px;">
            Sứ mệnh của tôi là giúp giải thích những khái niệm phức tạp theo cách dễ hiểu, truyền cảm hứng cho các nhà phát triển không ngừng mở rộng kỹ năng và kiến thức của mình. Thông qua các hội nghị, hướng dẫn và tài nguyên trực tuyến, tôi chia sẻ chuyên môn của mình với cộng đồng lập trình viên toàn cầu, mang đến cho họ công cụ và sự tự tin để phát huy hết tiềm năng. Với cách tiếp cận thực tiễn và cam kết đơn giản hóa những điều phức tạp, tôi nỗ lực trở thành chất xúc tác cho sự phát triển và học hỏi trong thế giới công nghệ AWS.
        </td>
    </tr>
</table>



