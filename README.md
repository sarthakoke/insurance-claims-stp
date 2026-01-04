# Intelligent Auto-Insurance Claims Decisioning  
### A Case Study on Process Improvement & Safe Automation

---

## 👋 Overview

This is a **self-driven solo case study** where I explored how basic automation and decision-making could be introduced into auto-insurance claims processing using **only a single CSV file**.

The goal of this project was **not** to build a production system or detect fraud.  
Instead, I focused on **business analyst thinking**:

- Understanding an operational problem  
- Using data to support decisions  
- Designing a realistic future-state process  
- Making sure automation is safe, explainable, and practical  

---

## 🤔 Why I Chose This Project

Many data projects stop at charts or dashboards.  
I wanted to go one step further and ask:

> *If a business only had this data today, what decisions could it reasonably automate — and where should humans stay involved?*

Insurance claims felt like a good example because:
- They are high-volume  
- Many claims are small and routine  
- Manual review is expensive  
- Automation must be done carefully  

---

## 📂 Data Used

I intentionally limited myself to **one CSV file** to keep the project realistic.

The dataset contained historical auto-insurance claim records, including:
- Claim amount  
- Coverage type  
- Vehicle class  
- Employment status  
- Income  
- Number of open complaints  
- Monthly premium  
- Customer lifetime value  

There was **no fraud label** and no final claim outcome.

I treated this as a realistic constraint, because many projects start with incomplete data.

---

## 👀 What I Noticed First

The first thing I looked at was the **distribution of claim amounts**.

One thing stood out immediately:
- About **two-thirds of all claims were $500 or less**

That raised a simple question:

> *Does it make sense for every claim to require the same level of manual review?*

That question became the foundation of the entire project.

---

## 🧩 The Problem (Current State)

For this case study, I assumed a simple current process:

- Every claim is reviewed manually  
- Average handling cost ≈ $150 per claim  
- Average processing time ≈ 7 days  
- No automated triage  

### Issues with this approach
- High cost for low-value claims  
- Slow turnaround for simple cases  
- Skilled staff spend time on routine work  

---

## 🎯 Project Objective

Design a **proposed future process** that:
- Automatically handles very simple claims  
- Sends uncertain cases to a human reviewer  
- Reduces manual workload safely  
- Keeps decisions explainable  

This naturally led to the idea of **Straight-Through Processing (STP)**.

---

## 🔄 What STP Means *Here*

In this project, STP simply means:

> Automatically approving very simple, low-risk claims end-to-end, while routing anything uncertain to a human.

Important clarifications:
- STP **does not deny claims**
- STP **does not detect fraud**
- STP **only decides routing**

Automation stops whenever confidence drops.

---

## ⚖️ Handling Risk Without Fraud Labels

Because there were no fraud outcomes in the data, I **did not attempt fraud prediction**.

Instead, I used simple **risk signals** as *confidence checks*, such as:
- Multiple open complaints  
- Missing or zero income  
- Claims that look unusually large compared to income  

These signals were only used to decide:
> *Is this safe to automate, or should a human review it?*

They were **never** used to approve or reject a claim.

---

## 🗂️ Claim Tiering Approach

Based on claim size and confidence checks, I designed three simple tiers.

### 🟢 Tier 1 — Auto-Approved
- Claim amount ≤ $500  
- Coverage information present  
- Few or no warning signals  

These claims are:
- Low financial risk  
- High volume  
- Good candidates for automation  

---

### 🟡 Tier 2 — Fast Human Review
- Medium-sized claims  
- Or small claims that failed one simple check  

These go to a **quick review queue**.

---

### 🔴 Tier 3 — Full Review
- Large claims  
- Or claims with multiple warning signals  

These remain fully manual.

---

## 📊 What the Data Showed (Simulation)

Using conservative rules:
- About **50% of all claims** qualified for Tier 1
- Estimated manual handling savings:
  - 4,588 claims × $150 ≈ **$688,000** (on sample volume)

This is a **directional estimate**, not a real forecast.

---

## 🔁 Proposed Future Process (To-Be)

### High-level flow:
1. Claim is submitted  
2. Required fields are checked  
3. Simple decision rules are applied  
4. Claim is routed:
   - Tier 1 → auto-approved  
   - Tier 2 → fast review  
   - Tier 3 → full review  

### Design principles:
- Humans remain involved  
- Automation is conservative  
- Every decision is explainable  
- Overrides are allowed  

---

## 🛡️ Controls & Governance

To keep automation safe, I designed:
- Adjustable thresholds (no hard-coding)  
- Manual override options with reason logging  
- Audit logs for every automated decision  
- Monitoring metrics such as:
  - % auto-approved  
  - override rate  
  - exception rate  

---

## 📝 Requirements Thinking

I translated the process into:
- User stories  
- Functional requirements  
- Non-functional requirements  
- Acceptance criteria  

The focus was on:
- Clarity  
- Safety  
- Auditability  

---

## ⚠️ Limitations

This project intentionally had limits:
- No fraud outcomes  
- No real policy systems  
- Simplified assumptions  

These were documented openly rather than hidden.

---

## 🔮 What I Would Improve Next

If extended further:
- Validate rules using real claim outcomes  
- Gradually relax rules based on results  
- Pilot automation on a small segment  
- Refine thresholds using post-launch data  

---

## ✅ Key Takeaways

This project helped me practice:
- Structured problem framing  
- Working with incomplete data  
- Balancing automation and risk  
- Thinking beyond dashboards  
- Explaining decisions clearly  

---
