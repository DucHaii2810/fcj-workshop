---
title: "Blog 2"
date: 2026-10-27
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# What should you keep in mind when starting with AWS to avoid any "nasty surprises" on your end-of-month bill?

One of the most common situations for beginners exploring AWS is accidentally spinning up a test resource and forgetting to turn it off, only to receive an unexpected bill at the end of the month. Controlling costs not only gives you peace of mind while practicing, but is also a foundational skill in cloud infrastructure management.

Below are the essential setups and considerations to help you manage your budget effectively right from day one.

1. Set Up AWS Budgets & Billing Alerts
   
- This is the very first step you should take right after creating your AWS account.

- Mechanism: Configure a safe budget threshold (for example, $5 or $10). When actual or forecasted costs exceed this threshold, the system automatically sends an email notification.
- Benefit: Prevents background resources from running continuously without timely detection.

2. Use the AWS Free Tier Properly
   
   The Free Tier provides many free resources, but it comes with specific conditions:

- Time limits: For instance, EC2 offers 750 hours/month for `t2.micro` or `t3.micro` instances (depending on the Region). If you run two instances simultaneously and continuously, usage hours are counted twice and will quickly exceed the free quota.
- Storage limits: Services like S3 and EBS have strict limits on storage capacity and request counts. Always read the service terms carefully before provisioning.

3. Clean Up Unused Resources

    "Orphaned" or standalone resources are frequently the cause of hidden charges:

- Stop or terminate EC2 instances: Shut down test servers whenever you are not actively working on them.
   
- Watch out for Elastic IPs: An Elastic IP is only free while attached to a **Running** EC2 instance. If it is disassociated or attached to a **Stopped** instance, you will still be billed an hourly maintenance fee.
   
- Delete Unattached EBS Volumes & Snapshots: When you terminate an EC2 instance, certain auto-created EBS volumes or snapshots may remain behind independently and continue incurring storage fees.

4. Track Usage in Detail with AWS Cost Explorer
    
- Visual tool: AWS Cost Explorer provides charts breaking down costs over time, by service, or by Tag.
- Regular checks: Making a habit of reviewing cost reports 1–2 times per week helps you quickly spot services consuming an abnormal share of your budget.

Summary
- Optimizing and controlling costs is an indispensable part of the Cloud Computing mindset. Setting up safe guardrails from the start allows you to comfortably learn and experiment with AWS services without worrying about unexpected bills.

[...Link... ](https://www.facebook.com/groups/awsstudygroupfcj/posts/2317495209015438/?notif_id=1793075766463069&notif_t=group_post_approved&ref=notif)