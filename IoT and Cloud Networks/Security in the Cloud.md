## Principle of Least Privilege 
- A fundamental concept stating every user should only receive the minimum necessary permissions to perform a specific task and no more.
- #### This is important because:
- It minimizes blast radius
- Reduces attack surface
- It makes way for better auditing & compliance
## Identity and Access Management (IAM)
- The "Who, What, and Which resource model"
- Manages identities and their permissions to access resources. Known as the "first line of defense"
- Differentiate the concepts of "<b>users, groups, and roles.</b>" Roles are particularly important in the cloud for applications and cross-account access.
- <b>Enforce the Principle of Least Privilege (PoLP):</b> Grant only the minimum permissions necessary for a user or service to perform it's functions.
- <b>Implement  Zero Trust architecture:</b> Never trust, always verify - verify every request regardless of origin.
- <b>Authentication (What You Can Do):</b> Controlled via policies (e.g., JSON documents specifying effect, action, and resource.)
### IAM - The "Who, What, and Which Resource" Model
- <b>Who (Principal):</b> The entity that requires access.
- <b>What (Role):</b> This defines which actions the principal is allowed to perform. Instead of assigning permissions, you assign a role.
- <b>Which Resource:</b> The specific Google Cloud resource you're granting access to.
### IAM - Types of Roles
- ###### Basic Roles (formerly Primitive Roles): Broad, Powerful roles:
	- <b>Owner:</b> Has full control over the projects, including billing and IAM policies.
	- <b>Editor:</b> Can create, modify, and delete most resources.
	- <b>Viewer:</b> Has read only access.
- <b>Predefined Roles:</b> These granular, service-specific roles are created and maintained by Google.
- <b>Custom Roles:</b> Custom roles created with specific set of permissions. Usually created when the predefined roles don't fit the specific needs.
### IAM - Policy
- Is a JSON object that binds one or more principles to a specific role.
- Is the official definition of who has what access.
- Is attached directly to a resource, contains a list of role bindings.
- Each binding specifies a role and list of participants who are granted that role.
### IAM - Resource Hierarchy and Policy Inheritance
A key feature of GCP IAM is that permissions are inherited down the resource hierarchy.
The hierarchy is structured as follows:
- Organization: The root node, which represents the entire company. 
- Folders: A way to group projects, often by department or team. 
- Projects: The fundamental unit for organizing resources. 
- Resources: The individual services, like a VM instance  or a Cloud SQL database.
## Authentication
The process of verifying that someone is who they claim to be.
- <b>The process:</b>
	- <b>Claim:</b> You claim an identity (e.g., you enter your username.)
	- <b>Verification:</b> The system challenges you to provide proof (e.g., a password.)
	- <b>Validation:</b> The system checks if the proof is sufficient and matches the records
	- <b>Result:</b> If it matches, you are authenticated and granted access. If not, access is denied.
### IAM - Authentication:
![[Pasted image 20251028151529.png]]
## Authorization
The process of determining what an authenticated user is allowed to do.
- <b>The Process:</b>
	- <b>Authorization</b> answers the question "Does this specific user have the permissions to perform this specific action on this specific resource?"
	- <b>Identity Confirmed:</b> The system knows who you are (e.g., user@example.org)
	- <b>Action Requested:</b> You try to do something (e.g., you click the delete button on the file report.docx)
	- <b>Permission Check:</b> The system consults its access control list or IAM policy:
		- Who?
		- Wants to do what?
		- On Where?
- <b>Result:</b> If a policy exists that grants this permission, the action is authorized and the file is deleted. If not, you receive a "Permission Denied" error. 
### IAM - Authorization
![[Pasted image 20251028152153.png]]
## Service Accounts:
- <b>Service Account:</b> A special non-human identity for an application (e.g., a VM) or another service. Like a robot's ID card
- <b>Key Identity, Not Permissions:</b> Just an identity, cannot do anything by itself.
- <b>Example:</b> An application running on a Compute Engine VM needs to write log data to a Cloud Storage bucket. The VM is assigned a service account, which acts as the application's identity when it calls the Cloud Storage API.
### Granting Permissions:
- To make a service account useful, you grant it permissions using IAM. IAM connects the who with the what and where.
- <b>Who? (Principal)</b>: The service account identity (e.g.,my-app-sa@my-project.iam.gserviceaccount.com)
- <b>What? (Role)</b>: A collection of permissions. Instead of assigning individual permissions, you assign a role like roles/storage.objectCreator, which contains all permissions needed to create objects in Cloud Storage
- <b>Where? (Resource)</b>: The specific Google Cloud resource you want to grant access to, like a project, a folder, or a single Cloud Storage bucket
- <b>Example:</b> To allow our application's service account to write to the logs bucket, we would create an IAM policy binding on that specific bucket:
	- Principal: my-app-sa@my-project.iam.gserviceaccount.com
	- Role: roles/storage.objectCreator
	- Resource: my-company-log-bucket
### The Full Workflow:
1) Authentication
2) API Request
3) Authorization
	- The Cloud Storage service receives the request and validates the token to identify the caller (my-app-sa@...)
	- It then checks its IAM policy for the bucket my-company-log-bucket
	- It finds the policy binding: "Does my-app-sa have the roles/storage.objectCreator role (or another role with the  storage.objects.create permission)?" 
	- Since we granted this role in Slide 2, the check passes.
4) Access Granted
### IAM Solution in Google Cloud:
- IAP is a cloud service that controls access to your applications based on a user's identity and the context of their request, not just their network location.
- The Core Problem IAP Solves: Traditionally, you'd protect internal apps with a corporate VPN. This is  often complex to manage and creates a broad network  perimeter. Once on the VPN, a user might have wide  access
- The IAP Solution: IAP shifts access control from the network level to the individual user. It verifies who the  user is and what they are allowed to access for every  single request, regardless of where the user is connecting from
### IAP in General
- ##### What Can You Protect?
	-  Web Apps: Running on App Engine, Cloud Run, Google Kubernetes Engine (GKE), and Compute Engine.
	- VM Access:  Securely tunnel SSH and RDP traffic to your Compute Engine instances, completely removing the need for public IP addresses or bastion hosts.
- Analogy: Think of IAP as a smart bouncer at an  exclusive club. It doesn't just check if you're on the "VPN  list." It checks your specific ID (your identity) and your invitation (your permissions) every single time you try to  enter a specific room (your application). 
### IAP Key Benefits
- Enhanced Security: Reduced application's attack surface. No longer need to worry about DDoS attacks.
- Simplified Access: Provides a seamless, secure way for employees and contractors to access  internal tools from anywhere without the hassle of a VPN
- Centralized Control & Auditing: Manage access for all your IAP-secured applications in one place (IAM). All access requests are logged in Cloud Audit Logs, giving you a clear view of who accessed what, and when. 
### IAP Example:
![[Pasted image 20251028153955.png]]
