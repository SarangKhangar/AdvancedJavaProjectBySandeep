Spring Cloud

It gives you many different libraries for implementing microservices

1] OpenFeign - use to make REST calls 

Steps to use OpenFeign

1] Add dependency in pom.xml

2] Create an interface with an method matching signature of remote 

3] Enable feign client
-----------------------------------------------------------------------------------------------------

 We want to assign unique name to every microservice and use that name to refer that microservice.
 It is by using 
 
 ----------------------------------------------------------------------------------------------------
 
   1) Eureka(8761) : 
                   
   It service registry and discovery server.
   Every mircosrvice register itself with Eureka
   Eureka server typically runs on port 8761
             
  ----------------------------------------------------------------------------------------------
  
   2) API Gateway(9090) :- 
   
   This is used to navigate calls to microservice
   All calls are first made to api gateway and then api gateway will route call to repsective microservice.
                   
 -----------------------------------------------------------------------------------------------
 
   3) Circuit Breaker :- 
   
   Circuit breaker is use in microservices to handle failure of services.
   It is implemented using a library given by spring cloud known as "resilience4j" 
                       
 ----------------------------------------------------------------------------------------------   
 
   4) Cloud Config Server(8888)

   It is a centralized application that manages all the application related properties. 
   #Following is common property for all microservices
   #If we need to change value of this commom property we need to go all the microservices and change
   #If there are hundreds of microservices it is difficult to do so that time consuming
   #Hence common properties shoud be done written using
   company=zensar India

-----------------------------------------------------------------------------------------------------

   There are many microservices communication with each other via apigateway.
   Hence there are many calls. Hence it is difficult to debug(To find how calls are executing)
   To know this we have to use

------------------------------------------------------------------------------------------------------

   5] Sleuth

   It is used for distributed tracing.

   APIgateway------> displayservice-------->messageservice.

   [servicename, treceId,spanId]

   traceid - is unique for a request across all services
   spanId - is unique for a request within same service

   This log is generated by slueth
   But this is on console and going through all the logs for all the services on console is difficult and time consuming task
   
---------------------------------------------------------------------------------------------------------
  
   6] ZipKin
   
   It is server which shows logs in GUI from are generated by sleuth
   
--------------------------------------------------------------------------------------------------------

Steps to run microservice application 

 1] First run Eureka server  8761
 2] Run Config server        8888
 3] Run Zipkin server        9411
 4] Run API Gateway          9090
 5] Run microservices
 
-----------------------------------------------------------------------------------------------------------
   
   @EnableEurekaClient is an optional annotation to write in top of the client class. 
   But you have to have the dependency of eureka client.
                   
                       
                       
                       
                       
                       
                       
                       
                       
                               
                   
              