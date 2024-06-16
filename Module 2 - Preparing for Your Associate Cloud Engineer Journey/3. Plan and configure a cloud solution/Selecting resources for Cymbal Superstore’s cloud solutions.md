Compute options in Google Cloud include those based on virtual machines as well as those based on containers. The level of controller flexibility needed by your solution could also be factors in deciding the correct compute product to use in a solution.

Similarly, data solutions in Google Cloud are based on the needs of the application. Throughput and latency will determine how quickly your application responds. 

* This Cymbal Ecommerce app is currently based on containers and needs to have global availability and low latency.
* CS would like to use Google Services to keep track of truck location.
* Logistics has a transportation management app implemented locally through a custom message broker.
* They would like to use Google Cloud to monitor the location of trucks for delivery status and analysis of mileage for preventative maintenance
* Third, Operations has decided to migrate their legacy supply chain application to the cloud.
* This is currently a virtual machine-based application based in a LINUX operating system, and is implemented with a lamp stack. 
* The application needs to be available local to CS HQ.

Cymbal Superstore's Ecommerce application is currently implemented with containers, so you decide to us Google Kubernetes Engine, of GKE, for compute. For storage, you select Cloud Spanner to house Cymbal Superstore's Ecommerce data, because it allows for global availability and low latency. 

Seeing as the Ecommerce system is a web-based application, you will need an external HTTPS load balancer. With GKE, you can do this by implementing an ingress object with a GCE ingress class. Applying that manifest will create an external load balancer for you. 

Logistics transportation management system currently uses an on-premise message broker. Together with the cloud architect, you choose Pub/Sub as a solution to collect sensor data from trucks for analysis in the cloud. You will use cloud functions to pull data from Pub/Sub and start a dataflow pipeline. Data flow will feed data into Cloud Bigtable to store your sensor data. You can run federated queries in BigQuery to visualize your data in Looker.

Moderating and analysis of this data is done close to headquarters. So Cymbal opts for a regional VPC solution for this application. 

Cymbal Superstore's existing supply chain application is implemented using virtual machines with a LINUX operating system and a common LINUX, Apache, MySQL, PHP

After analyzing this application's need, the cloud architect determines that the recommended cloud solution is to migrate this application to compute engine virtual instances. The data solution uses a cloud SQL instance configured with a MySQL database. The recommended network access would be external HTTPS access to the region for partners and internal connectivity between the application and the backing database service. 