# Service Mesh with HashiCorp Consul

## Kantapon Hemmadhun 6510545276

---

This project is part of the final exam for a DevOps course.
The setup is based on the tutorial: **[Consul Service Mesh Tutorial for Beginners [Crash Course]](https://www.youtube.com/watch?v=s3I1kKKfjtQ) By TechWorld with Nana**.

This repository includes:
1. GoogleCloudPlatform's microservices-demo source codes from [GoogleCloudPlatform/microservices-demo](https://github.com/GoogleCloudPlatform/microservices-demo) repository:
    - **`adservice`** - Delivers text-based advertisements based on contextual keywords.
    - **`cartservice`** - Manages and stores users' shopping cart items using Redis.
    - **`checkoutservice`** - Handles the checkout process by retrieving the cart, processing payment, arranging shipping, and sending order confirmation emails.
    - **`currencyservice`** - Converts currency values using real-time exchange rates from the European Central Bank.
    - **`emailservice`** - Sends order confirmation emails to users (mock implementation).
    - **`frontend`** - Provides the website’s user interface and session management without requiring user authentication.
    - **`paymentservice`** - Simulates credit card payment processing and returns a mock transaction ID.
    - **`productcatalogservice`** - Supplies a catalog of products from a JSON file, supporting product searches and detail retrieval.
    - **`recommendationservice`** - Suggests additional products based on the user's shopping cart contents.
    - **`shippingservice`** - Calculates shipping costs and generates mock shipment details based on the cart contents.
2. Terraform scripts from [twn-youtube/consul-crash-course](https://gitlab.com/twn-youtube/consul-crash-course) repository:
   - **`providers.tf`** – Defines the required AWS provider and its version for the Terraform project.
   - **`data.tf`** – Fetches a list of available AWS Availability Zones to use in infrastructure deployment.
   - **`variables.tf`** – Declares input variables such as VPC CIDRs, subnets, Kubernetes version, AWS region, and access credentials.
   - **`main.tf`** – Provisions AWS infrastructure, including a VPC with public/private subnets, an EKS cluster, node groups, IAM roles, and installs the EBS CSI driver addon.
3. Kubernetes manifest files from [twn-youtube/consul-crash-course](https://gitlab.com/twn-youtube/consul-crash-course) repository:
   - **`config.yaml`** — Standard Kubernetes Deployment and Service resources for microservices without Consul.
   - **`config-consul.yaml`** — Kubernetes manifests with Consul Connect service mesh integration, including sidecar injection and upstream service configurations.
   - **`consul-values.yaml`** — Helm chart configuration to deploy Consul on Kubernetes with Connect, Mesh Gateway, and UI enabled.
   - **`consul-mesh-gateway.yaml`** — Configures Consul to enable mesh gateways for cross-cluster communication.
   - **`service-resolver.yaml`** — Defines service failover policies for Consul when a service becomes unavailable.
   - **`intentions.yaml`** — Security policies (intentions) that control which services are allowed to communicate across peers.
   - **`exported-service.yaml`** — Declares which services are exported for peering with external clusters.
   - **`debug-pod.yaml`** — A simple `curl` pod deployed for debugging and testing service connections inside the cluster.
   - **`values-examples-with-explanations.yaml`** — A Helm values file example with detailed comments explaining each setting for Consul deployment.

## Acknowledgements
- **GoogleCloudPlatform/microservices-demo**: Provided the base e-commerce microservices application used in this project.

- **TechWorld with Nana**: Provided the tutorial and base Kubernetes/Terraform templates used to build the project.


