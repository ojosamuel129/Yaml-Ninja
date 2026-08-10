
# ☸️ Kubernetes YAML Architect

📌 Project Overview
This project is a hands-on introduction to Kubernetes YAML configuration and Infrastructure as Code principles.
The objective was to build a Kubernetes Pod manifest from the ground up while learning how Kubernetes resources are structured using YAML.
Rather than creating the complete configuration in one step, I built the manifest progressively. This helped me understand how Kubernetes uses API versions, resource types, metadata, specifications, lists, and indentation to define the desired state of a workload.
The final configuration creates a Pod named nginx-pod containing an Nginx container using the nginx:latest image.

🎯 Objectives
During this project, I worked on:
Creating a dedicated project workspace
Initialising a Git repository
Creating a Kubernetes YAML manifest
Understanding apiVersion
Defining a Kubernetes resource with kind
Adding resource metadata
Naming a Kubernetes Pod
Understanding YAML nesting and indentation
Creating a container list
Defining a container name
Specifying a container image
Applying Infrastructure as Code concepts
Organising configuration for version control

🧰 Technologies & Tools
Technology
Purpose
Kubernetes
Container orchestration platform
YAML
Kubernetes configuration format
Git
Version control
Nginx
Container image used by the Pod
Terminal
Creating and managing project files

📂 Project Structure
The project is organised around the Kubernetes manifest:
yaml-architect/
├── .git/
├── README.md
└── pod.yaml

The main configuration file is:
pod.yaml

🏗️ Building the Kubernetes Manifest
The manifest was created incrementally to understand what each section contributes to a Kubernetes resource.

1. Project Setup
First, I created a dedicated directory for the project:
mkdir -p ~/yaml-architect
cd ~/yaml-architect

This provides an isolated workspace for the Kubernetes configuration.
I then initialised Git:
git init

Using Git allows changes to the infrastructure configuration to be tracked over time.

1. Defining the API Version
The first entry in pod.yaml is:
apiVersion: v1

The apiVersion field identifies the Kubernetes API version used by the resource.
For this Pod, the core Kubernetes API version is v1.
The file was initially created with:
echo "apiVersion: v1" > pod.yaml

1. Defining the Resource Type
Next, I specified that the resource should be a Pod:
kind: Pod

This was added with:
echo "kind: Pod" >> pod.yaml

The kind field tells Kubernetes what type of object the YAML describes.
At this stage, the manifest contained:
apiVersion: v1
kind: Pod

1. Adding Metadata
Kubernetes resources use metadata to store identifying information.
I added:
metadata:
  name: nginx-pod

This was built using:
echo "metadata:" >> pod.yaml
echo "  name: nginx-pod" >> pod.yaml

The indentation is important here.
The two spaces before name indicate that name belongs to the metadata section.
The Pod therefore has the name:
nginx-pod

1. Defining the Pod Specification
The spec section describes the desired configuration of the Pod.
I added:
spec:

using:
echo "spec:" >> pod.yaml

The spec section separates the resource's identifying information from its desired configuration.

1. Creating the Containers List
A Pod can contain one or more containers, so the container configuration is represented as a YAML list.
I added:
spec:
  containers:

using:
echo "  containers:" >> pod.yaml

The next line creates the first item in the list:

- name: nginx

using:
echo "  - name: nginx" >> pod.yaml

The - character represents an item in a YAML list.

1. Configuring the Nginx Container
Finally, I specified the container image:
image: nginx:latest

The command used was:
echo "    image: nginx:latest" >> pod.yaml

The indentation is significant because image belongs to the same container object as name.

📄 Final pod.yaml
After completing the configuration, the final manifest is:
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:

- name: nginx
    image: nginx:latest

This configuration describes a Kubernetes Pod called nginx-pod with one container named nginx.

🔎 Breaking Down the Manifest
The final YAML can be understood from the top down:
apiVersion
    │
    └── Kubernetes API version

kind
    │
    └── Type of Kubernetes resource

metadata
    │
    └── Resource identification
          │
          └── name: nginx-pod

spec
    │
    └── Desired Pod configuration
          │
          └── containers
                │
                └── nginx
                      │
                      └── image: nginx:latest

Key fields
Field
Description
apiVersion
Specifies the Kubernetes API version
kind
Defines the resource type
metadata
Contains identifying information
metadata.name
Names the Pod
spec
Defines the desired state
containers
Defines the Pod's containers
containers.name
Names the container
containers.image
Specifies the container image

🧩 YAML Concepts Practised
Key-Value Pairs
Basic YAML properties use a key followed by a value:
kind: Pod

Nested Objects
Indentation creates relationships between properties:
metadata:
  name: nginx-pod

Here, name is nested inside metadata.
Lists
A hyphen creates an item within a YAML list:
containers:

- name: nginx

Indentation
YAML relies on indentation to represent structure.
For example:
spec:
  containers:

- name: nginx
    image: nginx:latest

The indentation shows which properties belong to the Pod specification and which belong to the container.
Important: YAML indentation should use spaces rather than tabs.

🔧 Git & Version Control
Git was initialised at the beginning of the project:
git init

A typical workflow for the project can then be:
git status
git add .
git commit -m "Create Kubernetes nginx pod manifest"

This provides a history of changes made to the Kubernetes configuration.
For example, future changes to pod.yaml can be committed separately as the Kubernetes configuration becomes more advanced.

💡 Key Learnings
This project helped reinforce several fundamental Kubernetes concepts.

1. Kubernetes configuration is declarative
Instead of manually describing every action Kubernetes should perform, the YAML describes the desired state of the resource.
2. YAML structure matters
Indentation isn't simply for readability. It determines relationships between configuration properties.
3. Kubernetes resources have a consistent structure
The combination of:
apiVersion:
kind:
metadata:
spec:

provides a useful foundation for understanding many Kubernetes resources.
4. Containers are defined within the Pod specification
The container configuration is nested inside:
spec:
  containers:

This establishes the relationship between the Pod and the container it runs.
5. Git is useful for Infrastructure as Code
Keeping Kubernetes manifests under version control makes infrastructure changes easier to track, review, and manage.

☁️ Infrastructure as Code Connection
This exercise demonstrates the basic principles of Infrastructure as Code (IaC).
The Kubernetes configuration is represented as a file rather than being configured manually through a graphical interface.
That means the configuration can be:
Stored in Git
Reviewed by others
Changed incrementally
Reused
Shared through GitHub
Used as a foundation for more advanced Kubernetes deployments

🚀 Possible Next Steps
The basic Pod manifest can be expanded into a more complete Kubernetes project.
Potential improvements include:
Add Pod labels
Expose a container port
Add environment variables
Configure resource requests and limits
Add liveness and readiness probes
Create a Kubernetes Deployment
Create a Kubernetes Service
Add ConfigMaps
Add Secrets
Introduce namespaces
Add more advanced Git workflows

🏁 Project Outcome
The completed project demonstrates my understanding of the fundamentals of Kubernetes YAML configuration.
I created a Git-controlled project containing a Kubernetes Pod manifest that defines:
Pod
 └── nginx-pod
      └── nginx container
           └── nginx:latest image

The exercise provided practical experience with YAML structure, Kubernetes resource definitions, container configuration, and Infrastructure as Code concepts.

📚 Skills Demonstrated
Kubernetes fundamentals
YAML configuration
Pod manifests
Container configuration
Git & version control
Infrastructure as Code
Linux/terminal commands
Configuration management
Technical documentation

Built as part of my hands-on Kubernetes learning journey. ☸️
