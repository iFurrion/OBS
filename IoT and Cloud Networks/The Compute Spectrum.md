## GCP Compute Spectrum
- Left (High Control):
	- Infrastructure as a service -> Compute engine (GCE)
- Middle-Left (Orchestration)
	- Containers as a service -> Google Kubernetes Engine (GKE)
- Middle-Right (Abstraction)
	- Platform as a service -> App Engine 
- Right(Highest Abstraction/Serverless)
	- Cloud Run & Cloud Functions
In this list, most left would be toward managed infrastructure and most right would be toward dynamic infrastructure

### Google App Engine
### App Engine Standard 
- Analogy: High performance, custom build
- Mechanism: Runs code in language specific secure toolbox
- Key Features: Extremely fast scaling (seconds), scales to zero, specific runtimes like python java etc.
- Best for: Web applications and APIs with predictable traffic patterns needing rapid scaling
### App Engine Flex
- Analogy: A standard Engine block that you can modify 
- Mechanism : Wraps your application in a Docker container and runs it on managed Compute Engine VMs
- Key Features: Any language via Docker, SSH access, doesn't scale to zero.
- Best for: Applications needing custom libraries, background processes or a runtime not supported by standard. this is the natural bridge to our next topic
#### Examples:
PUT APP ENGINE YAML EXAMPLES FROM THE SLIDE HERE

### Google Cloud Run
#### How does it work?
- Built on Knative (Kubernetes)
- Core principle: it only runs your container when a request comes in
#### Key Features:
- Stateless Containers: Any language, Any binary, any library that can be put in a container
- Request driven: Scales up or down based on incoming HTTP requests
- Event Driven: Can be triggered by over 200 event sources via Eventarc (e.g., file upload to Cloud Storage, message on Pub/Sub )
- Fine Grained Pricing: Billed per 100ms of CPU/memory usage
INSERT GCLOUD RUN KEY FEATURES IMAGE FROM SLIDES

### Decision framework: which tool to run when
Insert image


### Real World Scenarios
- I have a new microservice for a REST API written in go -> Cloud Run, it's container based and scales to zero
- I want to resize an image every time it's uploaded to a bucket -> Cloud Functions, classic event driven, single purpose task
- I have a monolithic Django web app I need to migrate to the cloud -> start with App Engine Flexible or Compute Engine to dockerize. Then, refractor parts of it into Cloud Run services over time