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