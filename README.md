# Project-3-GitOps-project-with-Microservices

This Project is focussed towrads Online Boutique Project

This is a type of e-commerce platform, but unlike Amazon-type stores, it focuses on:
```
Niche or curated products
Unique / limited collections
Strong brand identity & style
Think of it as a digital version of a small, stylish fashion store.
```
<img width="1726" height="1096" alt="image" src="https://github.com/user-attachments/assets/2f7f7c9f-b95f-4ac3-99be-df6d8028e318" />


From a technical perspective, modern boutique apps are not built as a single application.

They are built using Microservices Architecture.

## $${\color{Red} \textbf{What Are Microservices} \ \}$$

Microservices is an architectural style where an application is broken into small, independent services, and each service:

Handles a specific business function
Runs independently
Communicates via APIs

## $${\color{Red} \textbf{Architectural Overview: Monolith vs. Microservices} \ \}$$

### $${\color{Orange} \textbf{The Monolithic Approach} \ \}$$
Analogy: A boutique run by a single employee handling greeting, inventory, payments, and shipping.

The Risk: High traffic creates severe operational bottlenecks. If that worker is unavailable, business halts entirely.

System Impact: Monoliths combine all logic into a tightly coupled codebase. They are simple to launch, but fragile, difficult to scale selectively, and prone to total system outages from single-point failures.

### $${\color{Orange} \textbf{The Microservices Approach} \ \}$$
Analogy: A store with specialized staff—dedicated cashiers, inventory leads, and fulfillment teams operating side-by-side.

The Benefit: Extra cashiers can be added instantly during peak sales without altering warehouse staffing.

System Impact: Microservices decouple business capabilities into independent, self-contained services that communicate via lightweight APIs. This enables targeted auto-scaling, fault isolation, and faster deployment cycles.

How the Boutique Works Behind the Scenes
Inside our online boutique, distinct mini-apps work in tandem behind the scenes:

Product Catalog Service: Holds all the photos, descriptions, and pricing for our curated collections.

Cart Service: Keeps track of what customers pick out while browsing.

Payment Service: Securely handles credit cards, digital wallets, and checkout transactions.

Order Service: Tracks the order status from the moment purchase is confirmed.

Shipping Service: Calculates delivery rates and feeds tracking updates back to the customer.

Frontend Service: Renders the beautiful UI that shoppers actually interact with.

## $${\color{Red} \textbf{How They Talk to Each Other} \ \}$$
Because these services live independently, they need efficient ways to chat. When a user clicks "Buy Now", a quick web request (via REST or gRPC) travels from the Frontend to the Order Service, which instantly pings the Payment Service. For background tasks—like sending a confirmation email—the app uses background message queues like Kafka or RabbitMQ so the user doesn't have to sit around waiting for a screen to load.

<img width="1451" height="1150" alt="image" src="https://github.com/user-attachments/assets/9a2e33dc-0e40-4026-bce6-3b9687c0e1e5" />


# Terraform-Setup

Installation of VS Code is necessary ---->
https://code.visualstudio.com/download

Terraform installation ----> https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli

<img width="938" height="522" alt="image" src="https://github.com/user-attachments/assets/a8a34741-1eb0-4596-a0f3-09a32d5c4e88" />

Extraction is needed 

<img width="843" height="83" alt="image" src="https://github.com/user-attachments/assets/a38dbd4e-2c13-4832-9f4d-9e979815a3cb" />

The Exe File should be extracted within the C drive and Path variables are to be set

EXE FILE LOCATION


<img width="819" height="233" alt="image" src="https://github.com/user-attachments/assets/2973a648-8100-4b1d-8ef2-b0edbc7d059e" />

ENVIRONMENT VARIABLE SETTINGS


<img width="880" height="829" alt="image" src="https://github.com/user-attachments/assets/d7f3b21c-df32-4ddb-8bc0-1c7d19080842" />

Once set 
AWS CLI is needed to connect your AWS account within your local machine to integrate the above tools in synchornoy using CMD version may be checked
<img width="922" height="615" alt="image" src="https://github.com/user-attachments/assets/98f90475-4338-449f-88ac-95418a1e08ad" />
aws configure can  be used to log in the account 

<img width="507" height="116" alt="image" src="https://github.com/user-attachments/assets/13d3d6e6-d9c3-48e0-ba7e-1c70135b3f5d" />
