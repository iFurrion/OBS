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

