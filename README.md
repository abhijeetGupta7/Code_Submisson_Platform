# **Advanced Microservices-based Code Compilation and Execution Platform**

A highly scalable and modular platform designed for compiling and executing code across multiple programming languages. The system is architected with microservices to ensure modularity, scalability, and real-time interactivity.

---

## **Table of Contents**
1. [About the Project](#about-the-project)
2. [Tech Stack](#tech-stack)
3. [Features](#features)
4. [Microservices](#microservices)
5. [System Architecture](#system-architecture)
6. [Getting Started](#getting-started)
7. [Project Repositories](#project-repositories)

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

![Architecture for Coding Platform Backend](https://github.com/abhijeetGupta7/Code_Submisson_Platform_BACKEND/blob/main/Architecture%20for%20Coding%20Platform%20Backend.jpg)

The following steps explain the flow of requests and responses in the platform:

1. **Client Interaction**:
   - The client sends a code submission request to the **Submission Service**.

2. **Problem Details Fetching**:
   - The **Submission Service** makes a synchronous request to the **Problem Admin Service** to fetch problem details.
   - The **Problem Admin Service** queries the MongoDB database to retrieve the requested problem details and sends them back to the **Submission Service**.

3. **Submission Entry**:
   - The **Submission Service** creates a submission entry in the database and adds the submission payload (with the updated code stub) to the **Redis queue**.

4. **Acknowledgement to Client**:
   - The **Submission Service** sends an immediate response to the client, confirming that the submission has been received.

5. **Code Evaluation**:
   - The **Evaluator Service** picks the submission payload from the Redis queue and evaluates the code.
   - It performs test case matching and determines the status of the submission (e.g., pass, fail, or error).

6. **Evaluation Queue**:
   - The **Evaluator Service** adds the evaluation result to another Redis queue.

7. **Submission Update**:
   - The **Submission Service** retrieves the evaluation result from the evaluation queue, updates the submission details in the database, and notifies the **WebSocket Service**.

8. **Real-time Client Feedback**:
   - The **WebSocket Service** sends a real-time update about the submission status (e.g., passed or failed) to the client.

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
