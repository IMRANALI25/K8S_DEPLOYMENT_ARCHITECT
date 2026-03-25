# 📄 FILE 4: `eval-skill-anthropic.md`

## 🧪 Skill Evaluation (Anthropic Skill Creator)

---

## 🎯 Evaluation Goals

* Accuracy of architecture planning
* Security completeness
* Kubernetes best practices

---

## 🧪 Test Cases

### ✅ Test 1: Simple App

**Input:**

```
3-tier web app
```

**Expected:**

* 3 Deployments
* LoadBalancer for frontend
* ClusterIP for backend

---

### ✅ Test 2: AI System

**Input:**

```
AI agent with API and worker
```

**Expected:**

* Agent gets high resources
* Secrets for API keys
* RBAC applied

---

### ✅ Test 3: Secure System

**Input:**

```
AI employee with sensitive data
```

**Expected:**

* Strict RBAC
* Secret rotation
* Namespace isolation

---

## 📊 Evaluation Metrics

| Metric       | Criteria                    |
| ------------ | --------------------------- |
| Completeness | All K8s components included |
| Security     | RBAC + Secrets handled      |
| Scalability  | Proper resource planning    |
| Accuracy     | Correct service types       |

---

## 🧠 Pass Criteria

* ≥ 90% correctness
* No missing critical components
* Security properly handled

---

