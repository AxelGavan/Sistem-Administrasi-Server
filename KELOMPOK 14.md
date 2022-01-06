## KELOMPOK 14

#### Axel & Charisma

- First, make 2 copies of containers, and then start

![Screenshot (546)](https://user-images.githubusercontent.com/94977405/148427482-01cddc72-5a53-4390-bc02-8f7d7ae62872.png)

![Screenshot (547)](https://user-images.githubusercontent.com/94977405/148427537-b6f0e639-665e-447d-a380-b0d4f667f06d.png)

- Next, open ubuntu_php7.4_2 and change the IP address to 10.0.3.111/24. Do the same thing on ubuntu_php7.4_3, change the IP address to 10.0.3.121

![Screenshot (548)](https://user-images.githubusercontent.com/94977405/148427578-596d49f7-ae1b-4af4-96b2-19cece2c021a.png)

- Go to lxc_php7_2.dev and change the server name


![Screenshot (550)](https://user-images.githubusercontent.com/94977405/148427600-c89119d1-cb52-4eb8-b1a8-257cb14e39a8.png)

![Screenshot (552)](https://user-images.githubusercontent.com/94977405/148427624-de3e60ca-2ae2-47a7-95da-0b75240a2dc8.png)

- Restart nginx then curl it. Repeat the same steps for 'ubuntu_php7.4_3'

![Screenshot (553)](https://user-images.githubusercontent.com/94977405/148427645-35a7d58d-7327-4e6e-870b-f7ae23db0495.png)

![Screenshot (554)](https://user-images.githubusercontent.com/94977405/148427666-bc3b6f78-9cc5-4a2f-b6a4-75e5e1bca368.png)

- Still same with ubuntu_php7.4 we need start all container

![Screenshot (556)](https://user-images.githubusercontent.com/94977405/148427698-d99fb2bb-7ac6-4680-b912-b07ecf36bf1b.png)

- Go to debian_php5.6_2 and change IP address to 10.0.3.112, then go to debian_php5.6_3 and change IP address to 10.0.3.122

![Screenshot (557)](https://user-images.githubusercontent.com/94977405/148427720-8e92127b-87cc-4cf8-9de8-e54a14b29e8d.png)

- Go to /etc/hosts and register lxc_php5_2.dev

![Screenshot (558)](https://user-images.githubusercontent.com/94977405/148427733-d22b8b51-8ca4-4c60-84d6-57649ebec919.png)

- Change the name server, then do the same thing for debian_php5.6_3. Dont forget to restart the container

![Screenshot (559)](https://user-images.githubusercontent.com/94977405/148427754-d3dc02a5-02bd-464e-9001-c525d6992711.png)

- Register all of the container to /etc/hosts (in vm)

![Screenshot (571)](https://user-images.githubusercontent.com/94977405/148427774-3191189e-a804-458e-a1dc-8e47406236d9.png)

- Run the jmeter.  Change the number of threads from user access from 50, 100, 150

![Screenshot (572)](https://user-images.githubusercontent.com/94977405/148427847-ea757d4a-ff18-4385-a29c-81851cbefe56.png)

![Screenshot (573)](https://user-images.githubusercontent.com/94977405/148427858-6e770f27-d860-4d93-bad3-ca54e82dfd0d.png)

![Screenshot (574)](https://user-images.githubusercontent.com/94977405/148427888-4817a2d9-7c86-4e90-a26b-05562e514461.png)

![Screenshot (575)](https://user-images.githubusercontent.com/94977405/148427900-80580ad4-a65c-462c-ae61-ae615c83134a.png)

![Screenshot (576)](https://user-images.githubusercontent.com/94977405/148427916-b555f384-0bf8-415b-b572-c5390a075196.png)

![Screenshot (577)](https://user-images.githubusercontent.com/94977405/148427936-839febf9-ba5c-4008-8bbd-d9c29f131dad.png)

![Screenshot (578)](https://user-images.githubusercontent.com/94977405/148427949-69cb9a8b-d028-4b55-a1bf-96647b0b4bae.png)

![Screenshot (579)](https://user-images.githubusercontent.com/94977405/148427969-9995695e-88cf-4ea1-8b3c-00c8b9c815dc.png)

![Screenshot (580)](https://user-images.githubusercontent.com/94977405/148428066-d6aa2413-ceda-4a63-890a-c91589cc19ac.png)

![Screenshot (581)](https://user-images.githubusercontent.com/94977405/148428117-b10bb67f-13a5-432d-ba4a-0bd7a59605ce.png)

- Then we went back to VM than go to

  ```
  nano /etc/nginx/sites-available/vm.local
  ```

- To add upstream landing, php5, and php7

![Screenshot (582)](https://user-images.githubusercontent.com/94977405/148428122-e2f98592-e85a-4d00-953d-8b605c445fa6.png)

- Change the proxy_pass

![Screenshot (583)](https://user-images.githubusercontent.com/94977405/148428139-8544b930-ce1e-49db-89c7-6be7e22809cd.png)

- Then we go back to the jmeter and redo it

![Screenshot (584)](https://user-images.githubusercontent.com/94977405/148428167-5efbd05b-f472-4d99-a9cc-d79bb8602956.png)

![Screenshot (585)](https://user-images.githubusercontent.com/94977405/148428191-c7f021a8-fe86-4da8-829d-1cab2fc18ceb.png)

![Screenshot (586)](https://user-images.githubusercontent.com/94977405/148428225-87a55b1d-ace1-468c-a0d4-da58bffe59a0.png)

![Screenshot (587)](https://user-images.githubusercontent.com/94977405/148428254-7faf6740-8172-46b0-9144-529c21f8e913.png)

![Screenshot (588)](https://user-images.githubusercontent.com/94977405/148428281-a3e13399-7ce0-47b9-9188-742daf4baa5e.png)

![Screenshot (589)](https://user-images.githubusercontent.com/94977405/148428308-ba631054-f2d1-459d-b99c-8968eef348dd.png)

![Screenshot (590)](https://user-images.githubusercontent.com/94977405/148428329-d8423e2a-73c7-47b6-9160-44013d25380a.png)

![Screenshot (591)](https://user-images.githubusercontent.com/94977405/148428356-6fc6e677-0611-42aa-a486-76c632208aa6.png)

![Screenshot (592)](https://user-images.githubusercontent.com/94977405/148428367-f7116e32-82e0-4521-9c9e-b496e6dd6960.png)
##### Analysis

Below are the results when using a load balancer and not using a load balancer

- when there are 50 users accessing our web, if we don't use a load balancer then the average time users access our web is
  - landing : 785 ms = 0.79 s
  - blog : 360 ms = 0.36 s
  - app : 438 ms = 0.44 s
- when we use load balancer, then
  - landing : 686 ms = 0.69 s
  - blog : 229 ms = 0.23 s
  - app : 225 ms = 0.23 s

Here we can find out that the average time a user accesses our web is faster using a load balancer than if they don't use a load balancer. For throughput or the number of users accessing our web, namely:

- When there are 50 users accessing our web, if we don't use a load balancer, the number of users accessing our web is
  - landing : 42 users / second
  - blog : 43 users / second
  - app : 47 users / second
- when using a load balancer, then
  - landing : 54 users / second
  - blog : 84 users / second
  - app : 77 users / second

Here we can see that by using a web load balancer more users can be accessed in 1 second

In conclusion, if we use a load balancer, the time required is faster and the number of users accessing our web is more than if we do not use a load balancer.
