## Exploring DevPod for Container-Based Development Environments

## Introduction

So I'm poking around looking for some options for creating container based dev environments. I've tried Gitpod (which I actually like) but I was looking for something simpler that I could run on the infra of my choice. Over time as I've talked to customers, particularly those working on full stack projects or devops projects across different types of environments I've seen them struggle with finding something sustainable for handingling dependencies in a relatively simple, reliable reproduceable way.  Even though I like that Gitpod streamlines the experience I periodically look around for something self-hosted, simple and customizable. Recently, I ran across **DevPod** from Loft Labs, that caught my interest.

## Why Reproducible Environments Matter

What I've found is that having reproducible environments isn't just about consistency... it’s about minimizing friction, to spend time iterating on ideas, issues or whatever the task at hand instead of building and managing environments. Till now I've mostly used Terraform to provision infrastructure and AWS (and occassionally GCP) to simplify access to resources. From an enterprise perspective I see how customers I've worked with are challenged with things like getting a new developer or SRE's to move across projects or work through different dependencies at different parts of their tech stack. 

Containerized development environments offers a few pretty helpful things: 


## Why DevPod? 

While Gitpod and other solutions have made cloud-based  environments popular, its great to have a bit more over my setup. I like that I have options for the desired target infrastructure (local, container, k8s or IaaS) depending on what I need. There are a few other things that I found attractive as well.. including: 

1. **Self-Hosted Control**: Unlike SaaS options, DevPod runs on selected infrastructure which is great if I'm using it for sensitive data
2. **Flexible Infrastructure: runs on the lcoal machine, in a single container, kubernetes on vm's. 
3. **Multiple IDE Options**: integrates with popular IDEs (VSCode, JetBrains, vim and browser options)
4. **Developer-Centric Features**: DevPod allows integration with existing Kubernetes clusters, providing flexibility for development workflows that demand cloud resources while retaining local control.
5. **Simple Configuration Management**: Supports GitOps-style workflows, making it easy to declare and replicate environments using version-controlled files.


## Installation and Configuration

DevPod can be installed locally (which will get you running pretty quickly). I tried it on a mac and on an ec2 images, both were pretty easy to get running.

### Prerequisites
- Docker integration: Docker, git
- Kubernetes integration: a pre-existing k8s cluster (kind in this example), kubectl, helm, git



### DevPod client installation
```
{
curl -L -o devpod "https://github.com/loft-sh/devpod/releases/latest/download/devpod-darwin-amd64" 
chmod +x ./devpod
sudo mv ./devpod /usr/local/bin/devpod
}

```


### Install the docker provider
The docker provider allows for provisioning a local docker container for development. Probably the simplest option for simple projects or roughing out something locally or perhaps writing a blog post. If you're adding a docker provider, that assumes Docker is installed and running properly. Using the Kubernetes provider assumes that a cluster is available and running for DevPod to reference.

```
{
devpod provider add docker
}
```


