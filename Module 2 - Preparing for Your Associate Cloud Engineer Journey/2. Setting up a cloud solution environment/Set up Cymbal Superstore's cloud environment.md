Cymbal Superstore is ready to start implementing the basic cloud infrastructure for their organization. Outcomes of this include establishing a resource hierarchy, implementing organizational policies, managing projects and quotas, managing users and groups, and applying access management. Setting up billing and monitoring the use of your cloud resources are also things to consider.

Finally, choosing how you interact with Google Cloud is an important decision as well.

Cymbal Superstore plans to migrate three applications to the cloud; 
* its supply chain application, which will run on virtual machines 
* its containerized Ecommerce application, which will use GKE
* its transportation management application, which will use cloud functions to track truck location


These applications correspond to three different departments; 
* Operations Managers, the B2B supply chain 
* logistic overseas transportation
* Sales and Marketing Department manages the Ecommerce application

![Hierarchy for Cymbal Superstore](../../Assets/Module-2/2.%20Setting%20up%20a%20cloud%20solution%20environment/hierarchy%20for%20Cymbal%20Superstore.png)

The Cymbal Superstore organization is at the top, followed by optional folders underneath, one for each division and one for each application. There are multiple projects under the B2B supply chain app folder, one for each environment related to Continuous Integration and Continuous Delivery, CICD, a developing, staging and production environment.

Other apps in the chart would have a similar project structure. As you set up the hierarchy, you will also need to grant organizational policies. For example, Marketing might need access to data in the supply chain system to see if inventory levels affected recent marketing campaigns. Giving Marketing the viewer permissions on the supply chain production environment might be a good choice to give them the access they need.

An associate cloud engineer could also be tasked with enabling Application Programming Interfaces, or APIs, within projects during setup. Cymbal Superstore's Ecommerce project requires access to Google Kubernetes and Cloud SQL as a database backend, and you need to enable the APIs for these services.

Setting up the cloud environment also involves granting members IAM roles to ensure they have the right access to projects, depending on the needs of their job and their role at Cymbal Superstore. For example, data analysts in the Marketing Department will need access to historic sales data in the Ecommerce system.

This is a great use case for BigQuery, Google's cloud-based data warehouse solution. How would we go about giving the proper access? New data analysts would be added to a group named "Data Analyst." 

Managing permission and roles at a group level is easier than keeping track of permissions for individual users. 
* Data analysts need access to the data in a data center table, so they would require BigQuery.dataviewer role at the proper level.
* Queries in BigQuery are executive as an executable job. So to submit a query, a data analyst would also need the BigQuery.jobs.create permission.
* This permission is included in the pre-defined role named BigQuery.user.

You would give the data analyst group access to this role in the production project. As a cloud engineer, you'll need to know how to manage Cymbal Superstore's users and groups in cloud identity, a service for managing users and groups, if you're not doing so, via Google Workspace.

Google Cloud's operations suite, which used to be called stack driver, provides metrics and logging services for all your services, resources and projects in your cloud environment. To monitor metrics for multiple projects, you set up project scoping. If Cymbal Superstore's operations department decides to monitor metrics across all three supply chain projects in the staging environment project, you will set staging as a scoping project and then add Dev and Production as monitored projects.

While migrating to Google Cloud, Cymbal Superstore will be moving some of its IT expenditure to operational expenses, and the different departments associated with each application will be responsible for compute and storage costs.

You'll need to create a different billing account for each group and link each project to the appropriate account. The department lead in Sales and Marketing expresses particular concern about the cost of housing its data warehouse in BigQuery, and how to optimize queries and storage.

![Billing for Cymbal Superstore](../../Assets/Module-2/2.%20Setting%20up%20a%20cloud%20solution%20environment/Billing%20account%20for%20each%20group.png)

You'll need to set up custom billing projects and alerts for this department. Each department will also need you to set up billing exports that can be used to track charges.

* As an IT administrator for Cymbal Superstore, you can always set up resources in the graphical console.
* If you have a combination of tasks you need to do often, you can automate resource management tasks on the command line.
* The Cloud SDK has a G-Cloud command set that allows configuration of Google Cloud resources as an executable script.
* You can use the command "gcloud config set" to configure default options, such as the project and compute region. Then if you don't give specific command line arguments, the SDK will use these defaults, which simplifies your code even more. 