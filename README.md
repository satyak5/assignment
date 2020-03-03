# Assignment
Docker-compose file for Kafka-Zookeper Cluster with Persistant Volume for Data and Logs on the VM.

Installing docker and docker-compose tools on the Ubuntu VM

 Log in to the server and run the following commands

	> sudo apt-get update
	> sudo apt-get install docker.io docker-compose

Create a directory and add the docker-compose.yml into the directory

	> mkdir kafka
	> cd kafka (Add the docker-compose.yml file here)
	
 add kafka-1, kafka-2 and kafka-3 hosts to the client /etc/hosts file
	
	> echo '0.0.0.0 kafka-1 kafka-2 kafka-3' >> /etc/hosts 
 
 To start the Zookeepr Kafka Cluster you can run the below commands
 
	> docker-compose up
	
Testing the Deployment

 To test the setup, You can install a tool called kafkacat
 
	> sudo apt-get install kafkacat

	> kafkacat -P -b kafka-1:19092 -t hello
	
 open a new terminal and run the below commands
	
	> kafkacat -C -b kafka-2:29092 -t hello
	
 Now, type few messages in the previous terminal and you could see them on the 2nd Terminal
