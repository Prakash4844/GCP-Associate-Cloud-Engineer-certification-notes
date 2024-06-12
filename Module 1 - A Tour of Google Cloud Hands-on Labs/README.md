# A Tour of Google Cloud Hands-on Labs

## Overview


### Google Cloud
Google Cloud is a suite of cloud services hosted on Google's infrastructure. From computing and storage to data analytics, machine learning, and networking, Google Cloud offers a wide variety of services and APIs that can be integrated with any cloud-computing application or project, from personal to enterprise-grade.


### Google Cloud Skills Boost
Google Cloud Skills Boost is where you can access Google Cloud’s entire catalog of labs and courses. You can discover learning paths, build in-demand cloud skills, track your activity progress, and validate your knowledge with badges. 


> [!WARNING]  
> If you have a personal or corporate Google Cloud account or project, sign out of that account. If you stay logged in to your personal/corporate account and run the lab in the same browser, your credentials could get confused, resulting in getting logged out of the lab accidentally.

---

## Lab Environment

* Clicking on the `Start Lab` button will start the lab environment and build a temporary environment in Google Cloud.
* When the timer reaches 00:00:00, you will lose access to your temporary Google Cloud environment.


## Accessing the cloud console

* A Google Cloud project is an `organizing entity` for your Google Cloud resources. It often contains resources and services; for example, it may hold a pool of virtual machines, a set of databases, and a network that connects them together. Projects also contain settings and permissions, which specify security rules and who has access to what resources.

* A Project ID is a unique identifier that is used to link Google Cloud resources and APIs to your specific project. Project IDs are unique across Google Cloud: there can be only one `qwiklabs-gcp-xxx....`, which makes it globally identifiable.

* The username provided by qwiklabs, which resembles `googlexxxxxx_student@qwiklabs.net`, is a Cloud IAM identity and principal.

## Projects

* A project is a container for resources like virtual machines, databases, and applications. It is used to organize and manage resources and permissions. A project consists of a set of users, a set of APIs, and billing, authentication, and monitoring settings for those APIs.

* Your project has a name, number, and ID. These identifiers are frequently used when interacting with Google Cloud services. You are working with one project to get experience with a specific service or feature of Google Cloud.

* The "Qwiklabs Resources" project is a shared resource in Google Cloud used for training purposes. It includes files, datasets, and machine images that are necessary for completing certain labs. This project is accessible from any Google Cloud lab environment you work in during your training.
  * Shared and Read-Only: It is shared with all students and you cannot delete or modify its contents.
  * Access: You can access these resources from every lab environment you work in.

* The Google Cloud project you use during your lab exercises is temporary:
  * Temporary Nature: The project and all its contents will be deleted when the lab ends.
  * New Projects for New Labs: Each time you start a new lab, you will get access to new Google Cloud projects. These are the projects where you will perform all lab activities, not in the "Qwiklabs Resources" project.

## Roles and permissions

* Navigation menu in left pane offers quick access to the platform's services and also outlines its offerings.

* Google Cloud Identity and Access Management (IAM) is a service that allows you to manage access control by defining who (identity) has what access (role) for which resource.

* The Principal column displays `googlexxxxxx_student@qwiklabs.net` (Your matches the username you signed in with). The Name column displays `student XXXXXXXX`. The Role column displays `Editor`, which is one of three basic roles offered by Google Cloud. Basic roles set project-level permissions and, unless otherwise specified, control access and management to all Google Cloud services.

| Role Name      | Permissions |
|----------------|-------------|
| roles/viewer   | Permissions for read-only actions that do not affect state, such as viewing (but not modifying) existing resources or data.|
| roles/editor   | All viewer permissions, plus permissions for actions that modify state, such as changing existing resources.|
| roles/owner    | All editor permissions and permissions for the following actions: manage roles and permissions for a project and all resources within the project; set up billing for a project.|


* Basic roles set project-level permissions and, unless otherwise specified, control access and management to all Google Cloud services.

* As an `editor`, you can create, modify, and delete Google Cloud resources. However, you can't add or delete members from Google Cloud projects.

* `Editor` role provides all viewer permissions, plus permissions for actions that modify state, such as changing existing resources.

* Expiring access can't be provided on Basic IAM roles such as `Editor, Viewer, Owner`

## APIs and services

* Google Cloud APIs are a key part of Google Cloud. Like services, the 200+ APIs, in areas that range from business administration to machine learning, all easily integrate with Google Cloud projects and applications.

* When a lab provides a new Google Cloud project for a lab instance, it enables many APIs automatically so you can quickly start work on the lab's tasks. However, when you create your own Google Cloud projects outside of the lab environment, you will have to enable APIs yourself.

* Most Cloud APIs provide you with detailed information on your project’s usage of that API, including traffic levels, error rates, and even latencies, which helps you quickly triage problems with applications that use Google services.