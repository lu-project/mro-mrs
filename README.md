# MRO-MRS
Integrate Microsoft R Open and Microsoft R Server on Lablup backend.ai

### Introduction

* Microsoft Azure: you know it! :D
* Backend.AI: A server-side framework that provides an API-based remote code execution in various languages and pre-configured runtimes.

## Goal

* Offer Lablup's Backend.AI customers a high-performance, highly scalable R and machine learning computation kernels
* Validate and demonstrate benefits of Azure integration for the Backend.AI customers

## Participants

* Joongi Kim (Lablup)
  - Integrate Microsoft R Server to Backend.AI
  - Integrate Azure Blob Storage to Backend.AI
  - Help other people by providing necessary modifications/extensions of Backend.AI

* Jonghyun Park (Lablup)
  - Build docker images for CNTK and Microsoft R Open

* Jeongkyu Shin (Lablup)
  - Provide an example machine learning problem solving case in CNTK
  
* Krit Kamtuo (Microsoft)
  - Provide an example to demonstrate the performance benefits of Microsoft R
  - Help other people to learn and use R

* Daewoo Kim (Microsoft)
  - Provide all necessary resources, including Azure VMs and documentation/guides

## Machine Learning Server(Microsoft R Server) installation steps
- Install [Microsoft Machine Learning Server](https://docs.microsoft.com/en-us/machine-learning-server/what-is-machine-learning-server) VM on Azure
- Or, deploy Microsoft Machine Learning Server VM on Azure Portal
- Administration Utility, Configure server for "One-box"
- Set a local admin password

Now you can access to 12800 port - endpoint of R server

## Swagger API integration
- Set up [Swagger API](https://microsoft.github.io/deployr-api-docs/) for Restful API service
- Request login URL http://SERVER-URL:12800/login with HTTP request body
```
{
    "username": "admin",
    "password": "your-admin-password"
}
```
- Generate access_token and get session_id http://SERVER-URL:12800/sessions
- Execute code with generated session_id http://SERVER-URL:12800/sessions/session_id/execute  

Reference paper :  
[APIs for operationalizing your models and analytics with Machine Learning Server](https://docs.microsoft.com/en-us/machine-learning-server/operationalize/concept-api)  
[Machine Learning Server swagger specification](https://microsoft.github.io/deployr-api-docs/)  
[REST Calls using PostMan for R server Operationalization](https://blogs.msdn.microsoft.com/mlserver/2017/02/24/rest-calls-using-postman-for-r-server-o16n/)  

