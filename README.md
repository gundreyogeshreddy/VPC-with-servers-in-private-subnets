# VPC-with-servers-in-private-subnets


𝙑𝙋𝘾 : Virtual Private Cloud(VPC) is a secure, isolated, scalable, private cloud hosted within a public cloud. 
By using,VPC we can create isolate networks, control traffic and deploy resources securely within our own virtual network environment.

𝙉𝘼𝙏 𝙂𝙖𝙩𝙚𝙬𝙖𝙮 : Network Address Translation(NAT) gateway should create in public subnet only.
NAT gateway will mask the ip address of the private subnet instance and shows the ip address of the instance in public subnet that is (Batsion Host or Jump Server).And Batsion host is created in public subnet onl,because without public ip address of batsion host,no use of batsion host.

𝙀𝘾2 :Elastic Compute Cloud(EC2) is a web service that provides secure, resizable compute capacity in the cloud.
In EC2,we can create instances.An EC2 instance is a virtual machine consists of it's own CPU,memory,storage and netwoking connections.

𝐀𝐮𝐭𝐨 𝐒𝐜𝐚𝐥𝐢𝐧𝐠 𝐠𝐫𝐨𝐮𝐩 : whenever our application is receiving more requests,auto scaling group can automatically adjusts capacity or automatically increase the number of servers to allow the incoming traffic for giving response in fast and reliable manner.

𝙇𝙤𝙖𝙙 𝘽𝙖𝙡𝙖𝙣𝙘𝙚𝙧 : Load balancing is a method of distributing network traffic equally to reach our application or server.

𝙏𝙖𝙧𝙜𝙚𝙩 𝙂𝙧𝙤𝙪𝙥𝙨 : Target Groups are used to route incoming traffic to instances registered in the target group.


𝙎𝙩𝙚𝙥𝙨 𝙩𝙤 𝙙𝙚𝙢𝙤𝙣𝙨𝙩𝙧𝙖𝙩𝙚 𝙖𝙥𝙥𝙨 𝙞𝙣 𝙥𝙧𝙞𝙫𝙖𝙩𝙚 𝙨𝙪𝙗𝙣𝙚𝙩 :
1.Create vpc with 2 availability zones , 2 public and private subnets,1 per availability zone(NAT gateways).
And along with this Internet Gateway is created and attached to the vpc and wil complete remaining setup automatically.

2.Create auto scaling groups by creating a launch template,network,set up group size and scaling policies,add notifications and tags.

3.Before installing applications in the servers,we should create Batsion host because without batsion host,we can't connect and install applications into the servers or ec2 instance in the private subnet.

4.Now,i'm using Mobaxterm terminal,With the help of batsion host ip address and .pem file ,we will connect to the instance in the public subnet.

5.After,we have to connect to the instance in the private subnet.For this we have to create the file and insert,copy and paste the .pem file and save it.Command is(vim Yogesh.pem)

6.Now,give read permission access to that file.(sudo chmod 400 Yogesh.pem).

7.Now,let's connect to the private instance with this command(ssh -i Yogesh.pem ubuntu@private instance ip address).Now,we are successfully connected or login to the ec2 instance in private subnet.

8.Now we are in the instance in private subnet.After,install applications in the instances and run the servers.(vim index.html)and(python3 -m http.server 8000)

9.Now we will see application is running(serving HTTP) ✅

10.Now,create the load balancer and attach or register instances in private subnet as target group.

11.Finally,access(DNS name) ip address from the internet and now we see our application on the UI.✅
