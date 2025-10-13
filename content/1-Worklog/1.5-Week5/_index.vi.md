---
title: "Worklog Tuần 5"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---



### Mục tiêu tuần 5:

* Kết nối, làm quen với các thành viên trong First Cloud Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu **Database Concepts**: <br>&emsp; + Database, Session, Primary Key, Foreign Key <br>&emsp; + Index, Partition, Execution Plan, Database Log, Buffer <br> - Phân biệt **RDBMS** và **NoSQL** <br> - Hiểu rõ sự khác nhau giữa **OLTP** và **OLAP**                                                                                             | 06/10/2025   | 06/10/2025      | [YouTube - Database Concepts](https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217) |
| 3   | - Tìm hiểu **Amazon Redshift**: <br>&emsp; + Data Warehouse, kiến trúc MPP, Leader/Compute Node, Columnar Storage <br>&emsp; + Redshift Spectrum, Transient Cluster, tối ưu chi phí <br> - Tìm hiểu **Amazon ElastiCache**: <br>&emsp; + Redis & Memcached, cơ chế cache dữ liệu, auto failover <br> - Thực hành **Lab 5 - Amazon RDS**, **Basic SQL**, và **Lab 43 - DMS & SCT (bị lỗi)** | 07/10/2025   | 07/10/2025      | [W3Schools SQL](https://www.w3schools.com/sql/default.asp) <br> [Amazon Redshift Docs](https://docs.aws.amazon.com/redshift/) <br> [NCBS Book](https://www.amazon.com/Database-Internals-Deep-Distributed-Systems/dp/1492040347) |
| 4   | - Ôn luyện và thực hành **Basic SQL**: <br>&emsp; + SELECT, INSERT, UPDATE, DELETE <br>&emsp; + JOIN, GROUP BY, ORDER BY <br>&emsp; + Thực hành các truy vấn cơ bản trên môi trường giả lập | 08/10/2025   | 08/10/2025      | [W3Schools SQL](https://www.w3schools.com/sql/default.asp) |
| 5   | - Tiếp tục luyện tập **Basic SQL nâng cao**: <br>&emsp; + Subquery, Aggregate Functions, Constraints <br>&emsp; + Thực hành tối ưu truy vấn và sử dụng khóa chính/ngoại | 09/10/2025   | 09/10/2025      | [W3Schools SQL](https://www.w3schools.com/sql/default.asp) |
| 6   | - Thực hành **Lab Amazon RDS**: <br>&emsp; + Tạo và cấu hình instance RDS <br>&emsp; + Kết nối, truy vấn và quản lý CSDL trên RDS <br>&emsp; + Thử nghiệm backup, snapshot và restore <br> - Tổng hợp kiến thức **Database Concepts, RDS, Redshift, ElastiCache** | 10/10/2025   | 10/10/2025      | [Notion - Amazon RDS](https://www.notion.so/Amazon-Relational-Database-Service-Amazon-RDS-288d1c243c6a80c3819fc2ae9a5475f5?pvs=21) |


### Kết quả đạt được tuần 5:

* Hiểu rõ **các khái niệm nền tảng về Database**, bao gồm:  
  * Database, Session, Index, Partition, Execution Plan, Buffer, Database Log  
  * Phân biệt **RDBMS** và **NoSQL**  
  * Hiểu sự khác nhau giữa **OLTP** và **OLAP** trong thực tế  

* Nắm được **kiến trúc và nguyên lý hoạt động** của các dịch vụ **AWS Database**:
  * **Amazon RDS** – Quản lý cơ sở dữ liệu quan hệ trên AWS (PostgreSQL, MySQL, v.v.)  
  * **Amazon Redshift** – Data Warehouse dùng kiến trúc MPP, tối ưu cho OLAP  
  * **Amazon ElastiCache** – Caching service giúp giảm tải truy vấn cơ sở dữ liệu  

* Đã **thực hành thành công** các bài lab:
  * **Lab 5 – Amazon RDS**: tạo, kết nối, thao tác và sao lưu dữ liệu  
  * **Lab Redshift**: hiểu cách tổ chức dữ liệu theo columnar storage  
  * **Lab 43 – DMS & SCT** (thử nghiệm, có lỗi trong quá trình chạy)  

* Thành thạo **các câu lệnh SQL cơ bản và nâng cao**, bao gồm:
  * SELECT, INSERT, UPDATE, DELETE  
  * JOIN, GROUP BY, ORDER BY  
  * Subquery, Aggregate Functions, Constraints  

* Hiểu được **mối quan hệ giữa các dịch vụ AWS Database** và **cách kết hợp chúng** trong hệ thống thực tế.

* Có khả năng **tổng hợp, đối chiếu và triển khai thực hành** giữa lý thuyết (Database Concepts) và môi trường AWS (RDS, Redshift, ElastiCache).

