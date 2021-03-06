# Credit-App

This application is a simple design of credit application service.

## Requirements

For building and running the application you need:

- [JDK 1.11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
- [Maven 4](https://maven.apache.org)
- [Lombok](https://projectlombok.org/)
    * For IntelliJ [Lombok IntelliJ Plugin] (https://plugins.jetbrains.com/plugin/6317-lombok)
    * For Eclipse [Lombok Eclipse] (https://projectlombok.org/downloads/lombok.jar)
- [Mysql](https://dev.mysql.com/downloads/mysql/)
    
For Twilio sms service, you have to sign up [Twilio](https://www.twilio.com)

   - Get AccountId, AuthToken and PhoneNumber from Twilio Dashboard.
   - Go to com.credit.application.service.constants.CreditApplicationConstants file and fill below constants with Twilio keys.
      
      ```java
       public static final String TWILIO_SMS_ACCOUNT_ID = "*******";
       public static final String TWILIO_SMS_AUTH_TOKEN = "*******";
       public static final String TWILIO_PHONE_NUMBER = "******";
      ```
 For mysql database integration,
 
  - You have to create user in your local server with as below:
  
         spring.datasource.url=jdbc:mysql://localhost:3306/credit
         spring.datasource.username=test
         spring.datasource.password=Test1234
 
  - You have to run following command in your local mysql server:
       
        CREATE DATABASE `credit` /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci */ /*!80016 DEFAULT E             ENCRYPTION='N' */;

        CREATE TABLE "CreditApplication" (
        'identityNumber' varchar(180) NOT NULL,
        'applicationStatus' varchar(120) NOT NULL,
        'creditLimit' decimal(10,2) NOT NULL,
        'lastApplicationResultDate' datetime NOT NULL
        )ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
        
        
 ## Running application
 
  - Firstly, you have to run credit-score-service by running CreditScoreApplicationService file on port 8080.
  
  - Then, you have to run credit-application-service by running CreditApplicationServiceApplication file on port 8081
  
  - After two service runned succesfully, you can use below postman commands to call endpoints.
        
 [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/cd0995a05baa322ee550)
       
      
