# 48-Hour Decision Pipeline Pre-Flight — Intake (v1.2)

**Purpose:** Collect the minimum inputs to run the forensic pre-flight.

**Hard rule:** If you cannot share repo access/zip **or** any real CI evidence, this converts to an **Evidence Gap Pack** (48h).

---

## How to submit (one message)

Send **one message** containing:

- ✅ Completed answers (copy/paste block below)  
- ✅ Repo access method (read-only access **OR** zip snapshot)  
- ✅ CI evidence for 2–3 runs (links or uploads):  
  - 1 successful run  
  - 1 failed/partial run (if available)

I reply with **“Inputs complete”** (clock starts) or **“Inputs incomplete → Evidence Gap Pack”** (and what’s missing).

---

## Copy/paste response block

### **Acknowledgement (required) — Confirm:**
- This is a forensic diagnostic, not implementation  
- Engagement may conclude **Go / No-Go**  
- Async-only (no calls)  
- The 48-hour clock starts **after** completeness is confirmed  

---

### **1) Ownership**
Name:  
Role/Title:  
Company (if different than profile):  
Delivery email:  
Owner vs delegate vs no-access:  

---

### **2) Scope lock**
Pipeline type:  
Pipeline purpose (2 sentences):  
**ONE** critical path to evaluate (entrypoint/job name):  

---

### **3) Evidence access**
Repo access method (read-only or zip):  
CI system:  
Links/uploads — successful run:  
Links/uploads — failed/partial run (if available):  

---

### **4) Minimal execution context**
Environments (one / staging+prod / >2):  
Prod requires explicit approval today? (yes/no/unsure):  
Most damaging failure mode (pick one):  

---

### **5) Optional speed-ups**
Existing run artifacts (paths/filenames):  
Known “dangerous knobs” (modes/configs/defaults):  

---

## Known concerns (optional)

**Experienced any of these? (multi-select)**  
- Same run, different result  
- Can’t prove what ran weeks later  
- Silent config/mode drift  
- Unsafe defaults reaching prod  
- Review/compliance friction  
- None of the above  

**Anything else that matters (max 3 sentences):**  
[write here]

---

## Readiness / clock start (required)

Confirm:  
- All required inputs are complete (or you accept Evidence Gap Pack)  
- No fixes are implemented in this engagement  
- You have submitted repo access/zip + CI logs/links in this message  