Here is your **production-quality `skill.md`** designed specifically for **Claude Code Skill Creator (Anthropic)** — structured, strict, and ready to drop into your repo.

---

# 📄 `skill/k8-planning-skill.md`

# 🧠 Skill: Kubernetes Deployment Planner (K8 Planning Skill)

## 📌 Skill ID

k8s-deployment-planner

---

## 🎯 Purpose

Generate **production-ready Kubernetes deployment plans (NO YAML, NO CODE)** for:

* AI-native applications
* Agentic systems
* Microservices architectures
* Secure AI employees

This skill focuses on **architecture planning**, not implementation.

---

## 🧩 Capabilities

The skill can:

* Identify system components → map to Deployments / StatefulSets
* Recommend Service types:

  * ClusterIP
  * NodePort
  * LoadBalancer
* Define:

  * ConfigMaps
  * Secrets (with lifecycle strategy)
* Design Namespaces for isolation
* Apply RBAC (Roles & RoleBindings)
* Allocate resource requests & limits
* Define inter-service communication
* Enforce security best practices

---

## 📥 Input Schema

```json
{
  "application_name": "string",
  "scenario_type": "ai_system | microservices | secure_agent | general",
  "components": [
    {
      "name": "string",
      "type": "frontend | backend | agent | worker | database | service"
    }
  ],
  "architecture_description": "string",
  "security_level": "low | medium | high"
}
```

---

## 📤 Output Format (STRICT MARKDOWN)

The output MUST follow this structure:

### 1. Overview

* Application description
* Architecture summary

### 2. Deployments & Pods

* List each component
* Deployment vs StatefulSet
* Replica count
* Justification

### 3. Services

* Service per component
* Type (ClusterIP / NodePort / LoadBalancer)
* Reasoning

### 4. Resource Planning

* CPU & Memory requests
* Limits
* Special handling for AI workloads

### 5. ConfigMaps

* Name
* Purpose

### 6. Secrets

* Name
* Usage
* Sensitivity level

### 7. Secret Lifecycle Management

* Rotation policy
* Expiry handling
* Compromise response

### 8. Namespaces

* Environment isolation strategy

### 9. RBAC Design

* Roles
* RoleBindings
* Service Accounts
* Least privilege enforcement

### 10. Inter-Service Communication

* Communication paths
* Protocols
* Internal DNS usage

### 11. Security Enhancements (MANDATORY for medium/high)

* Network Policies
* Pod Security Standards
* Encryption at rest
* Audit logging

### 12. Final Architecture Summary

* Key design decisions
* Scalability considerations

---

## ⚙️ Planning Logic

### Step 1: Component Classification

* Frontend → Stateless Deployment
* Backend → Deployment
* Database → StatefulSet
* AI Agent → High-resource Deployment

---

### Step 2: Service Mapping

* Public-facing → LoadBalancer
* Internal → ClusterIP
* Optional external → NodePort

---

### Step 3: Resource Strategy

* AI Agents → High CPU + Memory
* APIs → Moderate
* UI → Low

---

### Step 4: Configuration Strategy

* ConfigMaps → Non-sensitive configs
* Secrets → Credentials, API keys

---

### Step 5: Security Strategy

#### Low

* Basic RBAC
* Minimal secrets

#### Medium

* RBAC + Namespaces
* Secret rotation

#### High

* Strict RBAC
* Network Policies
* Secret lifecycle automation
* Zero-trust communication

---

### Step 6: Communication Design

* Use Kubernetes DNS: <service>.<namespace>.svc.cluster.local
* Prefer internal communication
* Avoid unnecessary exposure

---

## 🧠 Constraints

* ❌ DO NOT generate YAML
* ❌ DO NOT write Kubernetes manifests
* ❌ DO NOT include implementation code
* ✅ ONLY produce structured planning

---

## 🧪 Example Invocation

### Input

```json
{
  "application_name": "AI Task Manager",
  "scenario_type": "ai_system",
  "components": [
    {"name": "UI", "type": "frontend"},
    {"name": "Backend", "type": "backend"},
    {"name": "Agent", "type": "agent"},
    {"name": "Notifier", "type": "service"}
  ],
  "architecture_description": "Task management system with AI automation",
  "security_level": "medium"
}
```

---

### Expected Behavior

The skill should:

* Generate 4 Deployments
* Assign LoadBalancer to UI
* Use ClusterIP internally
* Allocate higher resources to Agent
* Include ConfigMaps + Secrets
* Apply RBAC
* Provide communication flow

---

## 🧪 Edge Cases Handling

### Case: Missing Components

→ Infer standard architecture (UI + API + DB)

### Case: High Security

→ Enforce:

* Strict RBAC
* Network policies
* Secret rotation
* No public exposure unless required

### Case: AI-heavy workload

→ Increase:

* CPU
* Memory
* Horizontal scaling consideration

---

## 📊 Evaluation Criteria (Used by Eval)

* Completeness (all K8s primitives included)
* Correct service type selection
* Proper RBAC design
* Security depth
* Scalability awareness

---




