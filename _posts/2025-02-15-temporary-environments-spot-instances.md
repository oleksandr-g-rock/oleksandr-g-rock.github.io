---
layout: single
title: "Temporary Environments: Why You Should Use Spot/Preemptible Instances"
date: 2025-02-15
categories: cloud finops devops
tags: [spot, finops, automation, ephemeral, aws, gcp]
author_profile: true
---

Temporary environments often live far longer than intended — and on expensive, permanent compute.  
For short-lived development or QA tasks, this is unnecessary cloud spend.

Use Spot Instances (AWS) or Preemptible VMs (GCP) instead.

## 🔹 Why it matters

**Cost efficiency:**  
Spot compute is typically **3–5x cheaper** than on-demand instances.

**Security:**  
Spot instances disappear automatically — nothing is accidentally left running.

**Resilience:**  
If your environment can be recreated instantly, your infrastructure is genuinely healthy.

**Team discipline:**  
Ephemeral environments encourage reproducibility and reduce manual drift.

## 🔹 How to implement it
- Use Spot for non-critical workloads, CI builds, integration tests  
- Add interruption handling (auto-recreate logic)  
- Tag everything with TTL metadata (`expire_at`, `cleanup=true`)  
- Use mixed instance policies for longer jobs  

Staging and test environments should not behave like mini-production.  
They should be cheap, reproducible, and disposable.