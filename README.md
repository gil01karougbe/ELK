# ELK
MY ELK STACK PROJECT

# 1. INTRODUCTION
 This project is about implementing Elasticsearch and Kibana in a Docker environment using docker-compose.I will be installing winlogbeat on my windows host machine to ship data to Elasticsearch and then test the visualization with Kibana.


# 2-COMPONENTS DESCRIPTION

### A-Elasticsearch
Elasticsearch is a distributed, scalable search and analytics engine based on Apache Lucene. It is designed to handle large amounts of data and provide fast search and real-time analyticscapabilities. Elasticsearch provides a RESTful API that enables you to search, analyze, and store data in near real-time.

###  B-Kibana
Kibana is a web-based visualization and analytics platform that allows you to visualize and explore data stored in Elasticsearch. It provides a wide range of visualization options, includingbar charts, line graphs, pie charts, and more. Kibana also provides features such as dashboarding, alerting, and reporting, making it a powerful tool for analyzing and monitoring data.

### C-Winlogbeat
Winlogbeat is a lightweight log shipper that allows you to forward Windows event logs to various output destinations, including Elasticsearch, Logstash, and Kafka.

# 3. PREREQUISITES
* Have Docker and docker-compose installed
* Basic understanding of ELK stack



# 4. TOPOLOGIE
In general there is 2 way of implementing ELK:
* Install Beats on endpoints and configure them to ship data(Logs,Network traffic,..) to Logstash which is in charge of parsing these imputs and then send them to Elasticsearch and from here to
      Kibana.
* Configure Beats to ship data directly to Elasticsearch and from here to Kibana.The main advantage of doing this is the use of less ressouces than when shipping data to Logstash like before.

![image](https://user-images.githubusercontent.com/98090770/235653946-f07af787-b69a-473a-ad91-68b9481a586e.png)


# 5. INSTALLATION

      $ git clone https://github.com/gil01karougbe/ELK.git

      $ cd ELK 

      $ docker-compose up

# 6. USAGE
Access the Kibana web interface to visualize and analyze logs.

      http://localhost:5601

# 7. WINLOGBEAT 7.16.2 SETUP
* Click on Add integrations and the select Beats only

* Next navigate to end of the page to find Windows Event Logs
* Click on it and follow the instructions to get winlogbeat up and running
![image](https://user-images.githubusercontent.com/98090770/235656880-4b3deabf-6d71-4efa-9365-7b9b4fe2265c.png)
![image](https://user-images.githubusercontent.com/98090770/235657000-bd1eb87b-6304-4b12-9261-478debe28214.png)
![image](https://user-images.githubusercontent.com/98090770/235657138-e4b083d6-5644-46a3-8802-fe51da35c880.png)
![image](https://user-images.githubusercontent.com/98090770/235657225-4e68ada3-4158-492c-8612-3ce2a0a2cfc1.png)
![image](https://user-images.githubusercontent.com/98090770/235657295-66157e96-1154-426d-b9b0-cac63822f4d5.png)
![image](https://user-images.githubusercontent.com/98090770/235657493-bd7761ec-b914-4225-a463-390b3f3e3cd2.png)
![image](https://user-images.githubusercontent.com/98090770/235657691-5c92436b-4678-4275-8d24-1902799983e1.png)

# 8. CONCLUSION
In conclusion, the implementation of Elasticsearch and Kibana in a Docker environment using Docker-Compose and shipping data to Elasticsearch via Winlogbeat for visilization has proven to be ahighly effective solution for managing and analyzing large volumes of data.
  By utilizing Docker, we were able to quickly and easily set up a scalable and portable environment for our Elasticsearch and Kibana instances. With the addition of Winlogbeat, we were able toseamlessly stream data from Windows event logs directly into Elasticsearch for real-time analysis and visualization.

 Overall, this project has enabled us to gain valuable insights into our data and make informed decisions based on that analysis. By leveraging the power of Elasticsearch and Kibana in combinationwith Docker and Winlogbeat, we have created a robust and flexible platform for managing and analyzing data that can be easily replicated and scaled as our needs grow.
