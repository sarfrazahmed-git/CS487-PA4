<div align="center">

# PA4 Submission: TaskFlow Pipeline

<img alt="GitHub only" src="https://img.shields.io/badge/Submit-GitHub%20URL%20Only-10b981?style=for-the-badge">
<img alt="Total points" src="https://img.shields.io/badge/Total-100%20points-7c3aed?style=for-the-badge">

</div>

<div style="background:#f5f3ff;color:#111827;border-left:6px solid #6330bc;padding:14px 18px;border-radius:10px;margin:18px 0;">
Copy this file to <code style="color:#111827;background:#ddd6fe;padding:2px 4px;border-radius:4px;">SUBMISSION.md</code>. Put every screenshot in <code style="color:#111827;background:#ddd6fe;padding:2px 4px;border-radius:4px;">docs/</code>, embed it under the correct task, and write a short description below each image explaining what it proves. The grader should not need any file outside this repository.
</div>

## Student Information

| Field | Value |
|---|---|
| Name | Sarfraz Ahmed |
| Roll Number | 26100145 |
| GitHub Repository URL | https://github.com/sarfrazahmed-git/CS487-PA4 |
| Resource Group | `rg-sp26-26100145` |
| Assigned Region |`ukwest` |

## Evidence Rules

- Use relative image paths, for example: `![AKS nodes](docs/aks-nodes.png)`.
- Every image must have a 1-3 sentence description below it.
- Azure Portal screenshots must show the resource name and enough page context to identify the service.
- CLI screenshots must show the command and output.
- Mask secrets such as function keys, ACR passwords, and storage connection strings.


## Task 1: App Service Web App (15 points)

### Evidence 1.1: Forked Repository
![My Logo](PA44/t1-git-repo.png)

Description: image shows the repo forked into my github account.

### Evidence 1.2: App Service Overview
![My Logo](PA44/t1-webapp-ooverview.png)

Description: Name: pa4-26100145, res-group: rg-sp26-26100145, public-domain: pa4-26100145-cpcugqd2dudyakc6.ukwest-01.azurewebsites.net, location: UK-WEST, run-time: NODE-22.

### Evidence 1.3: Deployment Center / GitHub Actions

TODO: ![My Logo](PA44/t1-deployment.png)

Description: completed o-auth with the github, chose the rep, and asked azure to create yaml flow, changed root directory in yaml file. then the app pulled the code. 

### Evidence 1.4: Live Web UI

![My Logo](PA44/t1-appworking.png)

Description: TODO: You can see the app working in the web browser on the the public url of the web-app.

---

## Task 2: Azure Container Registry (15 points)

### Evidence 2.1: ACR Overview


TODO: ![My Logo](PA44/t2-acr-over.png)

Description: You can see the name, the manual said pa4 so stuck with it. resource group is: rg-sp26-26100145

### Evidence 2.2: Docker Builds


![My Logo](PA44/t2b1.png)
![My Logo](PA44/t2b2.png)
![My Logo](PA44/t2-b3.png)


Description: TODO: Explain which folder produced each image.

### Evidence 2.3: ACR Repositories

![My Logo](PA44/t2-acr-repos.png)

description: You can see all the images in the acr.

![My Logo](PA44/t2-p1.png)
![My Logo](PA44/t2-p2.png)
![My Logo](PA44/t2-p3.png)

Description: You can see all three of the images being pushed sucessfully.

---

## Task 3: Durable Function Implementation (12 points)

### Evidence 3.1: Completed Function Code

[function_app.py](function-app/function_app.py).

Description: TODO: Summarize how your orchestrator chains validation and report generation.

### Evidence 3.2: Local Function Handler Listing

![My Logo](PA44/t2-trigger_starting.png)
Description: You can see all the the functions being registered and local url of the http-starter

![My Logo](PA44/t2-local-val.png)
Description: local run of the function

---

## Task 4: Function App Container Deployment (8 points)

### Evidence 4.1: Function App Container Configuration

TODO: ![My Logo](PA44/t3-over.png)

Description: function name is rpa2610045  (pa-26100145 it was not allowing).

![My Logo](PA44/t3-func-enabled.png)
description:  all functions are enabled in the function app

![My Logo](PA44/t3-func-url.png)
description: You can see the correct image being deployed at function app

### Evidence 4.2: Orchestration Smoke Test

TODO: ![My Logo](PA44/t3-curl-start.png)

Description: TODO: status query and id being returned means that the the orchestrator was triggered. 

### Evidence 4.3: Expected Failed Status Before Downstream Wiring

![My Logo](PA44/t3-status-uri.png)

Description: at this stage since the app tries to call the validate url from the env vaiables but since it is not set it has to fail as there is no correct url to access validate service

---

## Task 5: AKS Validator (15 points)

### Evidence 5.1: AKS Cluster

![My Logo](PA44/val-serv-created.png)
description: development and services yamls applied


![My Logo](PA44/kuber.png)
description: on portaal the kubernates service deployed successfully


![My Logo](PA44/kub-creat1.png)
Description:node count : 1, node size: STANDARD B2s, region : UK-WEST ,resource group : rg-sp26-26100145.

### Evidence 5.2: Kubernetes Nodes and Pods




TODO: Embed screenshot of `kubectl get nodes` and `kubectl get pods`.

![My Logo](PA44/dep_running.png)
description: you can see validate deployment running


![My Logo](PA44/kuber-node.png)
Description: TODO: You can see the node being ready

### Evidence 5.3: Kubernetes Service

TODO: ![My Logo](PA44/EXTERNALIP.png).

Description: TODO: You can see the external ip: 51.140.242.47 and port : 8080

### Evidence 5.4: Validator API Tests

TODO: Embed screenshot of `curl /health`, a valid `curl /validate`, and an invalid `curl /validate`.
![My Logo](PA44/STATUS.png)
description:  health check is working

![My Logo](PA44/good_bad_ip.png)
descritpion: You can see both good and bath paths being called and implemented


### Evidence 5.5: Function App `VALIDATE_URL`

![My Logo](PA44/val-serv-created.png)

Description: You can see the validate url being set in the function app. the app validate function uses this env variable to hit the validate endpoint running in the aks.

### Evidence 5.6: AKS Idle Behavior

TODO: Embed AKS metrics screenshot and/or `kubectl` output after the service is idle.

Description: TODO: Explain that the AKS node remains running even when there are no orders.

---

## Task 6: ACI Report Job (15 points)

### Evidence 6.1: Blob Container

![alt text](PA44/reports_container.png)

Description: pdfs are generated by aci and stored in this container called "report" in the storage account.

### Evidence 6.2: Manual ACI Run

TODO: Embed screenshot of `az container show` for `ci-report-test`.
![alt text](PA44/container_manual_online.png)
description: command to run the manual container

![alt text](PA44/container_success.png)
description: you can see the container have been created

### Evidence 6.3: ACI Logs

TODO: 

Description: TODO: Explain what the report job printed after generating and uploading the PDF.

### Evidence 6.4: Generated PDF

![alt text](PA44/Test1.png) 

Description: the pdf is only written to the storage container because the aci wrote it here. 

### Evidence 6.5: Function App Managed Identity and IAM


![alt](PA44/mi.png)
Description: TODO: you can see the permissions for the managaged identity, accessed from the function app in which it is enabled. the contributer node is necasry to create the aci resource 

### Evidence 6.6: Report App Settings

![alt](PA44/env_vars.png)
![alt](PA44/env_vars2.png)

Description: you  can see the ACR env being set in the function app and Report envs being set. the are used to create an aci. that can connect to the acr and pull the image. You can also seet storage env variables that are used by the function app to access the storage account and also enable aci to write pdfs into it (in a container).

---

## Task 7: End-to-End Pipeline (15 points)

### Evidence 7.1: Web App Wiring

![alt](PA44/T1-ENV.png)

Description: The start url is used to start the job and then the staus url is used to track the status of it. 

### Evidence 7.2: Happy Path UI

![alt](PA44/starting_orch.png)
description: orchestration request sent to run

![alt](PA44/running.png)
description: orchestrator running

![alt](PA44/completed.png)
description order is completed cause it was a valid path.


Description: TODO: the order was less than 100 so it worked.

### Evidence 7.3: Backend Participation

TODO: Embed screenshots showing Function App invocation, AKS validator evidence, ACI evidence, and Blob PDF evidence.

![alt](PA44/starter_executed.png)
description: starter function has been executed

![alt](PA44/orchestrator_executing.png)
description: orchestrator started


![alt](PA44/executing_validate.png)
description: validater executed

![alt](PA44/report_activity_executing.png)
description: report function executing

![alt](PA44/orchestrator_executed.png)
description: ochestrator function executed

![alt](PA44/check-end-end.png)
description: here is the pdf generated and put into the container by the app.


### Evidence 7.4: Reject Path UI


![alt](PA44/rejected_browser.png)
description: the order value was greater than 100 so it is rejected



![alt](PA44/reject_path_only_val.png)

Description: TODO: the order quantity was greater than 100 so the backend does not move ahead validate

---

## Task 8: Write-up and Architecture Diagram (5 points)

### Evidence 8.1: Architecture Diagram

TODO: Embed your architecture diagram from `docs/`.

Description: TODO: Confirm that it shows GitHub, App Service, Durable Function, AKS, ACI, Blob Storage, ACR, and IAM.

### Question 8.2: Service Selection


The app service hosts the web interface. It provides a simple way to deploy the code from github without managing servers. Durable functions coordinate the steps. They keep track of progress and wait for slow tasks without wasting compute time. The azure kubernetes service runs the validator. It is ideal for always on background services that receive constant traffic. The container instance runs the report generator. It is a temporary worker that starts up to make a single document and then shuts down immediately to save money.

### Question 8.3: ACI vs AKS

![alt text](PA44/cost.png)
description: You can see that aci only costed when it was intitated. the kubernates served equal number of requests as well but costs much more as it keeps on runnning (though in this case i manually stoped it so the cost seems relatively less but still much higher than aci. )


When the kubernetes service is idle for ten minutes it stays active and keeps billing us. Idle for the temporary container instance means the program finished its work and the resource deleted itself. If someone spammed the submit button one thousand times the container instances would incur the most cost. This happens because every single click spawns a brand new container instance which charges a startup fee and runs individually. The kubernetes service just routes all the spam traffic to the same server so its cost does not change.

### Question 8.4: Durable Functions vs Plain HTTP

We use durable functions instead of plain web requests to avoid timeout issues. A standard web function will drop the connection and fail if a step takes too long. Building a document is slow so it needs a system that can wait patiently. Another issue is state persistence. If the document creation fails a plain function loses all memory of the user order. A durable function remembers the exact step that failed and allows the system to retry without losing the initial data.

### Question 8.5: Cost Review

![alt text](PA44/cost.png)

Description: the total one day cost seems to be around 3 dollars. the highest cost would be kubernates and the app service plan. in the image it shows less cause my kubernates service got stopped yesterday but the app service plan kept running. 

### Question 8.6: Challenges Faced

storage account was not allowing the function app to connect with. saw the slack message and fixed it.
the status_query_url was not working giving un-authorised. had to add more env variables so the mi can be used for storage as well. the it worked.

---
