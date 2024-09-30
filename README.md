## Exploring DevPod for Container-Based Development Environments

## Introduction

So I'm poking around looking for some options for creating container based dev environments. I've tried Gitpod (which I actually like) but I was looking for something simpler that I could run on the infra of my choice. Over time as I've talked to customers, particularly those working on full stack projects or devops projects across different types of environments I've seen them struggle with finding something sustainable for handingling dependencies in a relatively simple, reliable reproduceable way.  Even though I like that Gitpod streamlines the experience I periodically look around for something self-hosted, simple and customizable. Recently, I ran across **DevPod** from Loft Labs, that caught my interest.

## Why Reproducible Environments Matter

What I've found is that having reproducible environments isn't just about consistency... it’s about minimizing friction, to spend time iterating on ideas, issues or whatever the task at hand instead of building and managing environments. Till now I've mostly used Terraform to provision infrastructure and AWS (and occassionally GCP) to simplify access to resources. From an enterprise perspective I see how customers I've worked with are challenged with things like getting a new developer or SRE's to move across projects or work through different dependencies at different parts of their tech stack. 

Containerized development environments offers a few pretty helpful things: 
