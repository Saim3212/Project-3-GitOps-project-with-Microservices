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

## $${\color{Red} \textbf{ArgoCd Configure} \ \}$$

Installation Commands
```
kubectl create namespace argocd
```
```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
```
watch kubectl get pods -n argocd
```
```
sudo curl --silent --location -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/v2.4.7/argocd-linux-amd64
```
```
sudo chmod +x /usr/local/bin/argocd
```
```
kubectl get svc -n argocd
```
```
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'
```
```
kubectl get svc -n argocd
```
Change the Inbound Rules in security for the 2 Wanderlust instances as well

<img width="657" height="453" alt="image" src="https://github.com/user-attachments/assets/f075382a-075a-403a-b4f7-2876d79ccf15" />
<img width="1613" height="484" alt="image" src="https://github.com/user-attachments/assets/5ac68283-8113-421b-b9b8-d2aa1b7462b1" />

To get password paste in 

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

for adding Repo 
<img width="2032" height="370" alt="image" src="https://github.com/user-attachments/assets/d041fa89-a66c-422f-bddf-b3627179a192" />
Add in given options
<img width="908" height="817" alt="image" src="https://github.com/user-attachments/assets/0fc7da7e-fbdc-43b1-9ba6-fff90865e228" />

Add in SonarQube in Jenkins

Link in the URL from SonarQube
<img width="773" height="886" alt="image" src="https://github.com/user-attachments/assets/836473b3-683b-492d-8f41-f43fea832a57" />

Add in commands to push the git repo

```
git add .
```
```
git commit -m "update instance id" 
```
Login Argo inside Instance Change the IP according to the Argo IP 
```
 argocd login 52.53.156.187:32738 --username admin
```
<img width="1353" height="127" alt="image" src="https://github.com/user-attachments/assets/1d965e0d-2950-47b9-9f06-99e9c50935ac" />
<img width="528" height="125" alt="image" src="https://github.com/user-attachments/assets/d4667e5e-ece1-4d2d-9159-05eaf9e7a47a" />

get Argo Cluster List with Command
```
kubectl config get-contexts
```
edit the Cluster Command according to the name of the cluster and the Cluster name 
```
argocd cluster add Wanderlust@wanderlust.us-west-1.eksctl.io --name wanderlust-eks-cluster
```
<img width="1883" height="170" alt="image" src="https://github.com/user-attachments/assets/d58754bc-a100-4f0b-b790-477b98d31409" />
Once made , it should reflect within ArgoCD
<img width="2005" height="516" alt="image" src="https://github.com/user-attachments/assets/bd349ca0-64a7-407a-9abc-ecbf31161987" />

Create new application within Argo CD
<img width="2538" height="1221" alt="image" src="https://github.com/user-attachments/assets/3facbd0f-0356-4d86-984a-c8e9befd9ab0" />

And the application should now be active and healthy 
<img width="676" height="560" alt="image" src="https://github.com/user-attachments/assets/289b9c5e-1d29-48c1-951a-8b6e2dc47d94" />
make path as
```
 kubernetes
```
<img width="1997" height="1195" alt="image" src="https://github.com/user-attachments/assets/fc6eb94b-532a-453a-91fe-2353bd4e0708" />


