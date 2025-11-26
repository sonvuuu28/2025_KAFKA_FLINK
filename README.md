# Kafka & Flink Quick Start

## ⚡1. Mục đích repo
Repo này hướng dẫn cách setup **Kafka** và **Apache Flink** một cách nhanh chóng, đồng thời cung cấp các tutorial cơ bản để làm quen với:

- Kafka producer/consumer, topic, schema registry
- Flink stream processing kết nối trực tiếp với Kafka

## 📂2. Cấu trúc repo
```
Kafka-Flink
├── 📄 FLINK_tutorial.pdf # Hướng dẫn kết nối Flink với Kafka, chạy stream processing, test job
├── 📄 KAFKA_tutorial.pdf # Hướng dẫn cơ bản Kafka: tạo topic, producer, consumer
├── 📝 README.md
└── ⚙️ docker-compose.yml # File cấu hình tất cả service: Kafka, Schema Registry, Connect, ksqlDB, Flink
```

## 🐳3. Docker Compose

- **broker**: Kafka broker (PLAINTEXT + CONTROLLER)
- **schema-registry**: Quản lý schema (Avro)
- **connect**: Kafka Connect (data generator)
- **ksqldb-server / ksqldb-cli / ksql-datagen**: Thử nghiệm stream với ksqlDB
- **rest-proxy**: REST API gửi nhận message Kafka
- **flink-jobmanager / flink-taskmanager / flink-sql-client**: Cluster Flink + SQL Client để chạy realtime stream processing kết nối Kafka

## 🚀4. Hướng dẫn nhanh

1. Khởi động stack:
```bash
docker-compose up -d
```

2. Test Kafka:

- Tạo topic, gửi và đọc message (xem tutorial KAFKA_tutorial.pdf)

3. Test Flink:

- Kết nối Kafka với Flink SQL Client, tạo table đọc topic, chạy query realtime (xem tutorial FLINK_tutorial.pdf)

## 📝5. Tham khảo
[Confluent Repo](https://github.com/confluentinc/cp-all-in-one)

là repo của Confluent, cung cấp các file Docker Compose “tất‑cả‑trong‑một” để nhanh chóng chạy Confluent Platform / Apache Kafka. Repo bao gồm nhiều cấu hình khác nhau cho community, enterprise, cloud, và cả các thiết lập bảo mật như OAuth.