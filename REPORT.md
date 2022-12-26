# TASKS
**David Zandundo Fuster 780500**

## **Task 1**
***The two services `accounts (2222)` and `web` are running and registered (two terminals, logs screenshots).***

- Accounts  (port 2222)

![Log accounts](image/Screenshot_3.png)

![Screen accounts](image/Screenshot_4.png)

- Web  (port 3333)

![Log web](image/Screenshot_5.png)

![Screen web](image/Screenshot_6.png)

## **Task 2**
***The service registration service has these two services registered (a third terminal, dashboard screenshots).***

- Registration (port 1111)

![Log registration](image/Screenshot_1.png)

As you can see in the browser window `http://localhost:1111` the two services are registered:

![Two services](image/Screenshot_7.png)

## **Task 2**
***A second `accounts` service instance is started and will use the port 4444. This second `accounts (4444)` is also registered (a fourth terminal, log screenshots).***

I have modified application.yml :
![application.yml](image/Screenshot_8.png)

Then we can launch the new service:
![Log Service](image/Screenshot_10.png)

Finally, in the Registration service we should see the new service:
![Two services](image/Screenshot_9.png)

## **Task 4**
***What happens when you kill the service `accounts (2222)` and do requests to `web`? Can the web service provide information about the accounts again? Why?***

We can see if we kill the microservice with port 2222 now it doesn't appear in Eureka dashboard:
![Only Two services](image/Screenshot_11.png)

Now we do a request to `http://localhost:3333/accounts/123456789` to check if the web service can provide accounts functionality:
![Service 44444](image/Screenshot_12.png)

Accounts service in port 2222 was killed, but accounts service in port 4444 is alive so the web service provides information about accounts using that service. It is working because I had a replica running and registered in eureka.