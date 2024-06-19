As an associate cloud engineer, you're expected to have the knowledge to implement specific compute solutions, including Compute Engine, Kubernetes Engine, Cloud Run and Cloud Functions. Understanding availability, concurrency, connectivity and access options for these services are keys to success as you deploy them to support your needs.

Solutions you implement in Google Cloud will also require data stores. Google Cloud's data solutions include products that utilize relational and no SQL data structures. There are different products that support transactional and analytical use cases. Some solutions are optimized for low latency and global availability. 

Properly implementing software-defined networking will ensure your application front ends are accessible, and your application back ends are secured.

* Cloud Marketplace is always a good place to go if there's a specific software stack you need to support on your Compute Engine instances.
* Cloud Marketplace, you don't have to reinvent the wheel and can have a development or production framework up and running in no time.
* A common devops practice is to deploy your infrastructure in a declarative way, and source control your configuration files. 
* Deploying resources via infrastructure as code reduces human error, and speeds up resource allocation.

![Proposed solution](../../Assets/Module-2/4.%20Deploying%20and%20Implementing%20Cloud%20Solutions./Proposed%20soln.png)

Their Ecommerce solution is based on container management provided by Google Kubernetes Engine. Data provided by the globally available, horizontally scalable capabilities of Cloud Spanner, and external HTTPS load balancing for user access. This use case also has a need for historical sales data to be analyzed by BigQuery, Google Cloud's modern data warehouse implementation. The transportation management cloud solution monitors Pub/Sub for incoming sensor data, triggers a cloud function as new messages are posted to a specific topic, and starts a dataflow job to transform data and save it into Bigtable. Finally, the supply chain application implements managed instance groups in Compute Engine. 

The back end store for this solution is Cloud SQL. Connectivity between the back end database and Compute Engine instances is via TCP internal to the VPC. For the supply chain app, external access will be achieved via regional HTTPS load balancer. Three ways you can interact with Google Cloud to work with and deploy services are via Cloud Console, the command line, and programmatically. 

1. You want to implement a compute instance for the Cymbal Superstore development team to start developing code. One of the ways you can do this is view the Google Cloud Console. The screenshot shows some of the settings you need to specify as you create this instance. The name of the instance, the region and zone where the instance resides, the machine configuration, the boot disk, network settings and any other persistent disks that you're going to attach to this virtual machine. 

![Compute Engine Instance](../../Assets/Module-2/4.%20Deploying%20and%20Implementing%20Cloud%20Solutions./Implement%20compute%20for%20ecommerce.png)

2. Cymbal Superstore's supply chain app needs this Cloud SQL back end. Here is an example of how you would do this via the command line interface.Notice the parameters required include the Name, Resources and Region. Remember, you can access the CLI by loading the Google Cloud SDK on your local machine. You can also use Cloud Shell, a cloud based terminal with a G-Cloud CLI already installed on it. 

![Cloud SQL](../../Assets/Module-2/4.%20Deploying%20and%20Implementing%20Cloud%20Solutions./SQL%20instance%20using%20CLI.png)

3. The transportation management system is using Cloud Functions. Cloud Functions give you the option of deploying your function code from the local directory where it resides. Here is an example of the command to deploy a cloud function with a Pub/Sub trigger from a directly on your local machine; trans_mg_function is going to be the name of the deployed function based on the logic in the directory. The runtime parameter specifies the Python interpreter you want to use as you parse the function. The trigger topic parameter is the Pub/Sub topic you want to monitor. The data sent to your function includes the Pub/Sub event data and metadata. 

![Cloud Functions](../../Assets/Module-2/4.%20Deploying%20and%20Implementing%20Cloud%20Solutions./Severless%20cloud%20function.png)