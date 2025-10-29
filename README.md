# Assignment 2: Advanced Analysis and Automation

## Overview of Assignment 2

Assignment 2 builds on Assignment 1 by adding:

1. Realistic security event generation (simulated attacks)
2. Anomaly detection (baseline vs attack patterns)
3. Automated alerting (real-time notifications)
4. Performance optimization (tuning ELK stack)

## Task 3.1

### Initial baseline logs.

![alt text](assets/baseline_auth.png)

![alt text](assets/baseline_firewall.png)

![alt text](assets/baseline_ufw_discover.png)

Generating attack logs for the attack spike logs

![alt text](<assets/Screenshot from 2025-10-28 21-32-24.png>)

### Spike in logs

![alt text](<assets/Screenshot from 2025-10-28 21-43-03.png>)

![alt text](<assets/Screenshot from 2025-10-28 22-31-16.png>)

### Dashboards after attack Spike 

![alt text](<assets/Screenshot from 2025-10-28 22-51-47.png>)

![alt text](<assets/Screenshot from 2025-10-28 22-52-29.png>)

Baseline log count: 

Total UFW logs:6452               
Total Auth logs:761         

Attack spike log count:

Total UFW logs: 6964
Total Auth logs: 1798

## Task 3.2: Alerting and Correlation

For your understanding:

Think of it like this:

Right now: we have to manually check Kibana to see if attacks are happening
After Task 3.2: The system will automatically alert us when attacks happen!

It's like having a security guard who shouts at us when something bad happens, instead of us having to watch cameras 24/7!

### what we need to do 

We need to set up 4 automatic alerts that will notify us when:

- Someone tries to brute force SSH (5+ failed logins in 5 minutes)

- A new unknown IP tries to connect (IP never seen before)

- Someone uses suspicious sudo commands (accessing /etc/shadow, passwd, etc.)

we also need 3 correlation rules that connect events together.

### Tool We'll Use: ElastAlert2

ElastAlert2 is like a robot that:

1. Watches Elasticsearch constantly
2. When it sees something suspicious (based on rules YOU write)
3. It sends you an alert (email, Slack, or just logs it)

### Install ElastAlert2

![alt text](<assets/Screenshot from 2025-10-29 00-36-39.png>)

### Configure ElastAlert2

![alt text](<assets/Screenshot from 2025-10-29 11-38-35.png>)

### Create Rules Directory

![alt text](<assets/Screenshot from 2025-10-29 00-40-10.png>)

### Create Alert Rules

#### Alert Rule 1: Brute Force Detection

![alt text](<assets/Screenshot from 2025-10-29 11-43-00.png>)

#### Alert Rule 2: New IP Detected

![alt text](<assets/Screenshot from 2025-10-29 11-43-29.png>)

#### Alert Rule 3: Suspicious Sudo Commands

![alt text](<assets/Screenshot from 2025-10-29 11-43-53.png>)

#### Alert Rule 4: Port Scanning Detection

![alt text](<assets/Screenshot from 2025-10-29 11-44-14.png>)


### Create ElastAlert2 Index

![alt text](<assets/Screenshot from 2025-10-29 00-52-32.png>)

### Run Elastalert

![alt text](<assets/Screenshot from 2025-10-29 22-49-12.png>)

### Generate Test Events on Ubuntu VM

![alt text](<assets/Screenshot from 2025-10-29 23-21-40.png>)

![alt text](<assets/Screenshot from 2025-10-29 23-23-18.png>)


![alt text](<assets/Screenshot from 2025-10-29 23-34-19.png>)

![alt text](<assets/Screenshot from 2025-10-29 23-39-26.png>)






