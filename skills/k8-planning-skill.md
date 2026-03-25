
# 📄 FILE 3: `k8-planning-skill.md`

## 🧠 K8 Planning Agent Skill

### 🎯 Purpose

Generate Kubernetes deployment plans for any architecture.

---

## 🧩 Skill Definition

```
Skill Name: K8s Deployment Planner
```

---

## 🧠 Input Schema

```json
{
  "application_name": "string",
  "components": ["list of services"],
  "architecture": "description",
  "security_level": "low | medium | high"
}
```

---

## ⚙️ Output Structure

* Deployments
* Services (ClusterIP / NodePort / LoadBalancer)
* ConfigMaps
* Secrets
* Namespaces
* RBAC Roles & Bindings
* Resource Limits
* Communication Flow
* Security Plan

---

## 🧠 Core Logic

1. Identify components → map to Deployments
2. Classify services:

   * Public → LoadBalancer
   * Internal → ClusterIP
3. Assign resources:

   * AI workloads → High CPU/Mem
4. Generate ConfigMaps & Secrets
5. Apply RBAC:

   * Least privilege
6. Define communication topology

---

## 🔁 Reusability

* Works for:

  * AI Apps
  * Microservices
  * SaaS platforms
  * Agentic systems

---

## 🧠 Example Invocation

```
Plan a Kubernetes deployment for an AI chatbot with API, DB, and worker.
```

---
