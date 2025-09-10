# CHAT-TCP-with-TIMEOUT 2023/02

![Badge](https://img.shields.io/badge/Educational-blue?style=for-the-badge&logo=academia) \
![PUCRS](https://img.shields.io/badge/Made%20at-PUCRS-blue?style=flat-square&logo=bookstack&logoColor=white)


> This project was developed as part of the Computer Networks Laboratory course during the undergraduate program at PUC-RS (Pontifícia Universidade Católica do Rio Grande do Sul). It is intended for educational purposes and may not be production-grade.


## TCP Chat System in C (Linux)

This project is a minimalist **TCP-based chat system** written in C, using Linux sockets and classic system calls. It features a **multi-client server** with threaded request handling and a **dual-port architecture** for separation of control and data streams — making it both educational and scalable. Communication occurs over:

* `Port 50007`: command signaling (`/lin`, `/out`, `/sai`)
* `Port 50008`: data transfer (text messages and files)

Each client manages sending and receiving through **separate processes**, enabling responsiveness and parallelism. The system supports up to 3 simultaneous logins, enforces a **login timeout**, and includes basic file transfer (up to 1500 bytes).

---

## 🌐 What is TCP?

**TCP (Transmission Control Protocol)** is a foundational protocol of the internet. It ensures **reliable, ordered, and error-checked** delivery of bytes between applications:

* **Connection-oriented**: initiates a handshake to establish a reliable session
* **Byte-stream abstraction**: delivers continuous streams of bytes, not discrete messages
* **Guarantees delivery**: lost packets are retransmitted; order is preserved
* **Used in**: HTTP(S), SSH, FTP, and — in this case — your very own terminal chat

---

## Key Features

* Dual socket interface for control and data
* Timeout for inactive users
* Broadcast and private messaging (`/msg`, `/mpv`)
* File sending with `/arq` command
* Server removes disconnected or unresponsive clients automatically

> Make sure to adjust `SERV_IP` on the client file before running. Server listens on **ports 50007 and 50008**.
