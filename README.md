# spring-boot-application-events
One of the most powerful features of the Spring framework is its Application Events feature, which allows <br>
developers to create custom event-driven applications. Spring Application Events are events that are triggered <br>
by the Spring framework. They are designed to be used in the development of applications that need to be aware <br>
of changes in the environment. Spring Application Events allow developers to create applications that can respond <br>
to changes in the application environment in real time. Spring Application Events are based on the concept of the <br>
Observer pattern. The Observer pattern is a design pattern in which an object is able to observe the state of another <br>
object and react accordingly. In the case of Spring Application Events, the observer is the application and the object <br>
being observed is the application environment. It helps in improving code reusability. It is great tool for async  <br>
intra-microservice-communication, just like we do async inter-microservice-communication using Kafka. Spring Application <br>
Events don't require any specific dependencies, just the application with spring-web will do. <br>

# What will this demo project will demonstrate?
Say, we are building Hospital Management System, and we are suppose to build discharge-patient-service. <br>
Which requires - Billing Service => Finalize the patient's bill, <br>
Record Service => updating their medical records, <br>
Housekeeping Services => to prepare the room for next patient, <br>
Notification Service => to send a notification to patient and relevant medical staffs. <br>

```
        //Conventional way of calling methods.
        /*  billingService.processBill();
            medicalRecordsService.updatePatientHistory();
            housekeepingService.cleanAndAssign();
            notificationService.notifyPatients();
        */
```
- Why we opt Spring Event then, what issue it solves?
Above piece of code has issue of Tight Coupling, can't be async call, difficult to extend, maintain or test. <br>
Spring Application Event Solves it.

# How to run and test this spring-event code :

- Run the springboot code, and then go to POSTMAN.
- Hit a POST request with

- URL=> http://localhost:8080/discharge/api/process

- Body =>
```
  {
  "patientId":"B278TR279",
  "patientName":"Aadi"
  }
```

- Find your Billing Service, HouseKeeping Service, Medical Records Service, Notification Service updates in console.

# Source to learn :

- https://www.baeldung.com/spring-events#:~:text=Spring%20allows%20us%20to%20create,in%20the%20publisher's%20transaction%20context. 

- https://docs.spring.io/spring-framework/reference/testing/testcontext-framework/application-events.html 