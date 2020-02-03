========================
Welcome To My Case Study
========================
Prerequrites
1. Kafka
2. MySQL
3. MongoDb
4. Some python libraries. eg. pymongo, pandas, matplotlib, pyspark, kafka, requests, os. 
5. An IDE for running the python code eg. Eclipse


Steps to start the case study
1. Download the cdw_sapp.sql in MySqL and execute the .sql in the query manager.
2. Start the Zookeeper server
	zookeeper-server-start.bat "The zookeeper.properties directory"
	It's in the config directory under the kafka installation directory.
3. Start the Kafka server
	kafka-server-start.bat "The server.properties directory"
	It's in the config directory under the kafka installation directory.
4. Import the project in the IDE
	In Eclipse it's
		File -> Import -> Projects from Folder or Archive
		Choose the folder that contains the zip file
		e.g Browse... -> (select Case_Study_Deepali_Pandit.zip -> Open -> Finish
5. Once the project is created. Open the MainEntryPoint.py in the editor. And then execute & follow the instructions.


To check the ETL
1. To check if kafka topics are created.
	To list Kafka topics
		kafka-topics --list --bootstrap-server localhost:9092
	To check messages of the topics on the console
		kafka-console-consumer --bootstrap-server localhost:9092 --topic Network
		kafka-console-consumer --bootstrap-server localhost:9092 --topic ServiceArea
		kafka-console-consumer --bootstrap-server localhost:9092 --topic Insurance
		kafka-console-consumer --bootstrap-server localhost:9092 --topic PlanAttributes
2. Databases that will be created in MongoDb
	1. health_insurance_market_place
	2. credit_card
	To check the databases on MongoDB Shell
		show databases
	To check the collections in the databases
		use database_name
		show collections 

Solutions if you face some issues while the execution.
1. If you face memory issues while ETL of the Healthcare database, try deleting the Kafka_logs folder. For that you need to,
	a. Shutdown the Kafka server & the zookeeper server from another console. 
		kafka-server-stop
		zookeeper-server-stop
	b. Delete the kafka_logs folder
	c. Start the zookeeper & kafka servers again.
2. If use get any class not found definition errors, you are probably missing one of the libraries.
   Try pip install LibraryName from the command prompt.
