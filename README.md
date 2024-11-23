# **Advanced Microservices-based Code Compilation and Execution Platform**

A highly scalable and modular platform designed for compiling and executing code across multiple programming languages. The system is architected with microservices to ensure modularity, scalability, and real-time interactivity.

---

## **Table of Contents**
1. [About the Project](#about-the-project)
2. [Tech Stack](#tech-stack)
3. [Features](#features)
4. [Microservices](#microservices)
5. [Getting Started](#getting-started)
6. [Project Repositories](#project-repositories)
7. [System Architecture](#system-architecture)

---

## **About the Project**
This platform facilitates online code compilation and execution, supporting multiple programming languages and providing real-time feedback. Designed with scalability and performance in mind, the system incorporates asynchronous processing, real-time communication, and efficient resource management.

Key Highlights:
- **Scalability**: Microservices ensure the system can handle increasing user demands.
- **Real-time Interaction**: WebSocket integration allows for instant feedback and interactivity.
- **Multi-language Support**: Docker containers provide isolated environments for safe and efficient execution.

---

## **Tech Stack**
### **Backend**
- **Express.js**: Framework for building RESTful APIs.
- **TypeScript**: Strongly typed language for enhancing maintainability.
- **Fastify**: High-performance framework for managing high request volumes.
- **MongoDB**: NoSQL database for managing dynamic problem sets.
- **Redis**: In-memory data store for caching and message queues.
- **WebSocket**: Real-time communication channel.

### **Containerization**
- **Docker**: Isolated environments for multi-language code execution.

---

## **Features**
1. **Dynamic Problem Administration**:
   - Manage CRUD operations for programming problems.
   - Include complex test cases and language-specific code stubs.
2. **Advanced Code Execution**:
   - Multi-language support (Java, Python, C++).
   - Efficient handling of Time Limit Exceeded (TLE) scenarios.
   - Strategy and Factory design patterns optimize execution environments.
3. **High-Performance Submission Management**:
   - Handles high volumes of code submissions seamlessly.
   - Asynchronous communication using Redis message queues.
   - Real-time feedback to users through WebSocket.
4. **Fault Tolerance and Scalability**:
   - Scalable microservices architecture ensures reliability under heavy loads.

---

## **Microservices**
### 1. **Problem Administration Service**
- Manages CRUD operations for programming problems, test cases, and code stubs.
- Repository: [Problem Admin Service](https://github.com/abhijeetGupta7/AlgoCode-Problem-Service)

### 2. **Executor Service**
- Handles code compilation and execution in Docker containers.
- Supports Java, Python, and C++ with optimized execution strategies.
- Repository: [Executor Service](https://github.com/abhijeetGupta7/AlgoCode_Evaluator_service)

### 3. **Submission Service**
- Processes user submissions, integrating with the executor service for result evaluation.
- Built with Fastify to handle high request volumes efficiently.
- Repository: [Submission Service](https://github.com/abhijeetGupta7/Algocode-Submission-Service)

### 4. **Socket Service**
- Provides real-time updates to users through WebSocket connections.
- Repository: [Socket Service](https://github.com/abhijeetGupta7/AlgoCode_Socket_Service)

---

## **System Architecture**
![System Architecture Diagram](https://via.placeholder.com/800x400.png?text=Add+Your+System+Architecture+Diagram+Here)

---

## **Getting Started**
### **Prerequisites**
- **Node.js**: v14.x or above.
- **MongoDB**: Latest stable version.
- **Docker**: Installed and configured for containerized environments.
- **Redis**: In-memory data store.

### **Setup**
1. Clone the repositories listed in the [Project Repositories](#project-repositories) section.
2. Follow the setup instructions in each repository’s README.

---

## **Project Repositories**
| Service                 | Description                                                    | Link                                                                 |
|-------------------------|----------------------------------------------------------------|----------------------------------------------------------------------|
| Problem Admin Service   | Manages problem sets, test cases, and language-specific stubs  | [Problem Admin Service](https://github.com/abhijeetGupta7/AlgoCode-Problem-Service) |
| Executor Service        | Compiles and executes code using Docker containers             | [Executor Service](https://github.com/abhijeetGupta7/AlgoCode_Evaluator_service) |
| Submission Service      | Handles user submissions and integrates with executor service  | [Submission Service](https://github.com/abhijeetGupta7/Algocode-Submission-Service) |
| Socket Service          | Provides real-time user feedback via WebSocket                | [Socket Service](https://github.com/abhijeetGupta7/AlgoCode_Socket_Service) |

---
