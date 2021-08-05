# springboot-resilience4j-with-actuator
An example of a Spring Boot project using Resilience4j with Actuator

This example is a Gradle version of: https://www.youtube.com/watch?v=LefFKbIFyjQ
I made a couple of changes:
1. This is using Gradle.
2. He included the Lombok dependency, but it was never used, so I removed it.
3. His source code did not include the Item-Service project. I created one.

Order-Service runs on port 8080
Item-service runs on port 8081

Steps to run:
1. Start/Run Order-Service.
2. Open browser and enter URL: http://localhost:8080/order. You should see in browser: Item service is down.
3. In PostMan or Browser, use the actuator URL: http://localhost:8080/actuator/health. You should see the state as HALF_OPEN.
4. Repeat Steps 2 and 3 for a total of 4 times.
5. Repeat Steps 2 and 3 one more time. The state will change to OPEN.
6. Start/Run Item-Service.
7. Repeat Steps 2 and 3 one more time. The state will change to CLOSED. You should see in browser: Item selected
