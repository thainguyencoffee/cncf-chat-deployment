# ¶ Chat Application - Chat Deployment

This is my first Cloud Native project. Learn more [Cloud Native](https://www.cncf.io/)

## ¶ Setup local Docker

> Đây là những thiết lập môi trường để chạy các ứng dụng tại local và sử dụng Docker, chưa liên quan tới Kubernetes

- Để chạy được dự án này bạn cần có docker và docker compose được cài đặt trên máy tính.
- Bạn sẽ không cần có các _data service_ chạy trên máy tính, thay vào đó bạn sẽ sử dụng _docker-compose_
- Clone dự án này về `git clone https://github.com/thainguyencoffee/cncf-chat-deployment.git`
- Di chuyển tới `/cncf-chat-deployment/docker`.
- Tham khảo bảng bên dưới để khởi chạy các dịch vụ khác nhau.
- Quay lại thiết lập tiếp cho các service bao gồm [cncf-edge-service](https://github.com/thainguyencoffee/cncf-edge-service/blob/main/README.md) và [cncf-api-service](https://github.com/thainguyencoffee/cncf-api-service/blob/main/README.md) nếu chưa thiết lập 
- Happy coding. 

| Lệnh                                                                   | Công dụng                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `docker-compose up -d postgres-service redis-service keycloak-service` | Khởi chạy tất cả backing service (recommend)                                                                                                                                                                                                                                              |
| `docker-compose up -d postgres-service`                                | Khởi chạy postgres database                                                                                                                                                                                                                                                               |
| `docker-compose up -d keycloak-service`                                | Khởi chạy keycloak                                                                                                                                                                                                                                                                        |
| `docker-compose up -d redis-service`                                   | Khởi chạy redis database                                                                                                                                                                                                                                                                  |
| `docker-compose up -d edge-service`                                    | Khởi chạy toàn bộ những thứ cần thiết như database, keycloak, cncf-api-service. <br> **Lưu ý:** Để chạy được lệnh này bạn phải đảm bảo đã clone **cncf-edge-service** và **cncf-api-service**. <br>Và đảm bảo chạy lệnh sau để build từng ứng dụng thành image `./gradlew bootBuildImage` |

