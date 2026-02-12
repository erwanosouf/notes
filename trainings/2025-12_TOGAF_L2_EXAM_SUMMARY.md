# TOGAF L2 (Practitioner) Exam - Quick Reference Summary

**Exam Date:** TBD  
**Duration:** 1H30  
**Format:** 8 case studies, 4 possible answers per question  
**Scoring:** 0, 1, 3, or 5 points per answer - Need > 24 points to pass  
**Resources:** Open book exam ✅

## 🎯 Exam Strategy

- ✅ **Make a first quick pass**, note doubts, come back later
- ✅ **First intuition is often good** - trust yourself
- ✅ **Go to exam center** (better environment)
- ✅ **If remote:** Keep eyes on screen, minimize noise
- ✅ **Key tip for L2:** **IDENTIFY THE PHASE** in each case study
- 🆔 **Bring 2 pieces of ID**

---

## 📚 Core Concepts Review

### TOGAF ADM (Architecture Development Method)

**⚠️ CRITICAL FOR EXAM:**
- **First phase = Preliminary Phase (Adapt)**
- **9 total phases in ADM, 8 phases in the cycle** (Preliminary + A through H)
- Process is **cyclical, iterative, and centered on Requirements Management**

### ADM Phases Structure

Each phase has:
- Objectives
- Approach (Steps)
- Inputs and Outputs (Deliverables)
- Techniques

**⚠️ Deliverable Statuses:** Only 2 possible states - "Draft" or "Approved"

### Key Validations

1. **End of Phase A (Architecture Vision):**
   - Validation of all Stakeholders, needs, constraints, budgets

2. **End of Phase F (Migration Planning):**
   - Overall Planning and Costing (Resources, Activities, Costs)

---

## 🔄 ADM Phases Deep Dive

### Phase Préliminaire (Preliminary)

**Purpose:** Define desired Architecture capability

**Deliverables 📗:**
- Architecture Framework
- Principles
- Repository
- Architecture Project Request (Template)

**Outputs:**
- Contextualized Architecture Framework
- Established architecture capability

---

### Phase A: Architecture Vision

**⚠️ CRITICAL:** This is where **Stakeholder Management** happens

**Key Deliverables 📗:**
1. **Architecture Vision**
   - High-level view of target capabilities
   - Business value delivered
   - Proposed EA

2. **Statement of Architecture Work (Définition de Chantier d'Architecture)**
   - Work approach
   - Scope
   - Stakeholders, Concerns, Requirements
   - Assess transformation team capability
   - Planning through end of Phase F

**Techniques:**
- Business Scenarios (SMART requirements)
- Stakeholder Management
- Readiness assessment for enterprise transformation

---

### Phase B: Business Architecture

**Focus:** Business domain

**Key Outputs:**
- Develop Target Architecture
  - Enables Architecture Vision
  - Conforms to Statement of Architecture Work
  - Addresses stakeholder concerns
- Identify components of potential Architecture Roadmap

**Techniques:**
- Business Scenarios (SMART)

---

### Phase C: Information Systems Architecture

**Focus:** Applications + Data

**Key Outputs:**
- Target Application Architecture
- Target Data Architecture
- Components of Architecture Roadmap

---

### Phase D: Technology Architecture

**Focus:** Technology domain

**Key Outputs:**
- Target Technology Architecture
- Components of Architecture Roadmap

---

### Phase E: Opportunities and Solutions

**Purpose:** Consolidation

**Key Deliverable 📗:**
- **First version of Architecture Roadmap**
- Definition of Solution Building Blocks (SBB) addressing Target Architecture

**Key Consideration:**
- Need for incremental approach?
  - Work package management (Gaps, Value, Dependencies)

**Technique:**
- Readiness for Business Transformation (re-evaluation using info from B, C, D)

---

### Phase F: Migration Planning

**Purpose:** Finalization

**Key Deliverables 📗:**
- **Architecture Roadmap** (finalized)
- **Implementation and Migration Plan**

**Note:** Multiple iterations possible between E and F

---

### Phase G: Implementation Governance

**Purpose:** Ensure conformance

**Key Activities:**
- Architecture Conformance Assurance
- Global Consistency Verification

**Key Deliverable 📗:**
- **Architecture Compliance Reviews** (based on SBB reviews)

---

### Phase H: Architecture Change Management

**Purpose:** Maintain architecture lifecycle

**Key Activities:**
- Active and updated Architecture lifecycle
- Architecture Governance Framework properly applied
- Architecture Capability aligned with Requirements

---

## 🔑 Requirements Management (Center of ADM)

**⚠️ CRITICAL:** Requirements Management applies to **ALL phases**

**Key Points:**
- Identify requirements downstream
- Go back upstream to unblock issues

**Example Flow:**
```
Business requirement (B) → Technical infeasibility (D) 
→ New Requirement → Return to B
```

---

## 👥 Stakeholder Management (Phase A)

**⚠️ IMPORTANT FOR EXAM**

### Process
1. **Identify Stakeholders (AC - Acteurs Concernés)**
2. **Group and Classify** stakeholder positions

### Key Deliverables 📗

1. **Stakeholder Analysis Matrix (Matrice d'Analyse des Acteurs Concernés)**
   - Disruption capability
   - Current and expected understanding
   - Required and expected commitment
   - Required support

2. **Power/Interest Matrix (Matrice Pouvoir/Intérêt)** 💡
   - Adapt approach based on influences and interests

3. **Stakeholder Map (Carte des Acteurs Concernés)**
   - Contextualize deliverables

### Architecture Views

**Two approaches:**
- Based on Stakeholder viewpoints
- Based on ad hoc View and generalize implicit viewpoint

**Benefits of viewpoint library:**
- Less work for architects
- Better stakeholder understanding (familiar viewpoint)
- Better confidence (known viewpoint history)

### Requirements Management

- **Stakeholders** = owners of Requirements, value, and prioritization
- **Architects** = responsible for Requirements, coherence, and traceability
  - Requires **Engagement** and **Communication**

**SME:** Subject Matter Expert

---

## 🏛️ Governance

**⚠️ Review carefully for exam**

**Definition:** Set of means and practices for steering and controlling Enterprise Architecture at all levels

**Principles:**
- Discipline
- Transparency
- Independence
- Accountability (Redevabilité)
- Responsibility
- Fairness (Équité)

### Architecture Board (Comité d'Architecture)

**Highest governance body**

**Responsible for:**
- Achievement of fundamental objectives
- Operational level
- Exercise of governance

**Key Activities:**
- Associate contracts to ADM phases
- Evaluate Conformance

---

## 🛠️ Key Techniques

### 1. EA Principles (CRICS)

**Structure:** Name + Statement + Rationale + Implications

**CRICS criteria:**
- **C**ohérent (Consistent)
- **R**obuste (Robust)
- **I**ntelligible (Understandable)
- **C**omplet (Complete)
- **S**table (Stable)

**Objectives:**
- Guide decision-making
- Ensure alignment with Strategy
- Aid governance
- Provide coherent approach

### 2. Business Scenarios

**Purpose:** Identify Business Requirements  
**Criterion:** Must be SMART  
**Used in:** Phase A and B

### 3. Gap Analysis

**⚠️ Key technique across phases**

**Purpose:**
- Ensure nothing is forgotten
- Identify Transition Architectures (intermediate steps)

**Gap types by domain:**
- **Business:** personnel, processes, finances
- **Applications:** to modify, create, eliminate
- **Data:** useless, obsolete, scattered
- **Technology:** to modify, create, eliminate

### 4. Readiness for Business Transformation

**Components:**
- Readiness Factors
- Position in **maturity model**
- Risk assessment
- **Capability Assessment Document**

**Used in:** Phase A and re-evaluated in Phase E (leveraging info from B, C, D)

### 5. Interoperability

Define level at each Phase

### 6. Architecture Alternatives

**⚠️ Technique based on:**
- Vision
- Principles
- Requirements

---

## 📦 Key Concepts & Definitions

### Artifacts vs. Deliverables

**⚠️ EXAM DISTINCTION:**

**Artifact:**
- Product of architectural work
- Describes an aspect of architecture
- Examples: Lists, Matrices, Diagrams

**Deliverable:** ⚠️
- Product of architectural work that is **contractually specified**
- **Formally reviewed and signed** by stakeholders
- Can contain artifacts

### Building Blocks

**Definition:** Component (potentially reusable) of a capability that can be combined with other Building Blocks

**To use Building Blocks:**
- Identify them
- Document them
- Procure them
- Integrate them

**Types:**
- **ABB** (Architecture Building Blocks)
- **SBB** (Solution Building Blocks)

### Architecture Views

- **Architecture Viewpoint:** Generic perspective from which an Architecture View is taken, restricted to a Stakeholder Concern
- **Architecture View:** Representation of a system that addresses a set of Concerns

---

## 📊 Content Framework

**⚠️ Appears in exam**

**Purpose:**
- Structural model to define, structure, and present all elements produced during ADM implementation
- Store templates and classify elements **without physically storing them**

**Key distinction:**
- **Real Architecture** vs. **Description of Architecture**

---

## 🔄 ADM Application Patterns

### Iteration

**Three types:**
- To manage an "Architecture Landscape"
- Within a Phase
- To manage Architecture capability

**Concept:** "ADM within ADM"

### Partitioning

**Three levels:**
- Strategic Architecture
- Segment Architecture
- Capability Architecture

### Purposes

- Strategic level Architecture
- Portfolio level Architecture
- Project level Architecture
- Solution Delivery level Architecture

---

## 📐 Architecture Scope

**Four dimensions:**
1. **Extent (Étendue):** Group, Enterprise, Business Unit
2. **Depth (Profondeur):** Granularity in terms of objects
3. **Time**
4. **Domains**

---

## 🎯 Key Architecture Domains

**Four main domains:**
1. Business
2. Application
3. Technology (Technologique)
4. Data (Données)

*Plus others including Security & Risks*

**Four abstraction levels:**
1. Contextual
2. Conceptual
3. Logical
4. Physical

---

## 📝 Important Acronyms & Terms

- **EA:** Enterprise Architecture
- **AE:** Architecture d'Entreprise
- **AC:** Acteurs Concernés (Stakeholders)
- **ADM:** Architecture Development Method
- **ABB:** Architecture Building Blocks
- **SBB:** Solution Building Blocks
- **SME:** Subject Matter Expert

---

## 🎓 Final Exam Tips

### Before the Exam

1. **Review all QCM warnings (⚠️)** - these are exam-likely topics
2. **Memorize key deliverables (📗)** - know which phase produces what
3. **Practice identifying phases** from scenario descriptions
4. **Understand stakeholder management** - critical for case studies
5. **Know the difference** between artifacts and deliverables
6. **Review governance principles** - frequently tested

### During the Exam

1. **Read each case study carefully** - identify the phase first
2. **Look for keywords** that indicate specific phases or techniques
3. **Remember partial credit** - 1 or 3 points for partially correct answers
4. **Use your open book** - but know where to look quickly
5. **Don't overthink** - trust your preparation and first instincts
6. **Time management** - 1H30 for 8 case studies ≈ 11 minutes per case

### Phase Identification Keywords

- "Initial setup", "define capability" → **Preliminary**
- "Stakeholders", "vision", "high-level", "approval" → **Phase A**
- "Business processes", "organizational structure" → **Phase B**
- "Applications", "data" → **Phase C**
- "Technology platform", "infrastructure" → **Phase D**
- "Consolidate", "opportunities", "first roadmap" → **Phase E**
- "Migration plan", "finalize roadmap" → **Phase F**
- "Implementation oversight", "conformance" → **Phase G**
- "Maintain", "change management", "lifecycle" → **Phase H**

---

## 📚 Recommended Resources

- [Why does Enterprise Architecture Matter?](https://publications.opengroup.org/w076) - See "So what are businesses?"
- [TOGAF Pocket Guide](https://pubs.opengroup.org/pocket-guides/togaf-pocket-guide/main/introduction.html)
- [Enterprise Architecture Principles](https://www.superblocks.com/blog/enterprise-architecture-principles)
- [TOGAF 7 Principles Examples](https://www.opengroup.org/architecture/togaf7-doc/arch/p4/princ/princ.htm#Example)
- [Archi: Software for Archimate Modeling](https://www.archimatetool.com/)

---

## ✅ Pre-Exam Checklist

- [ ] Review all ADM phases and their key deliverables
- [ ] Practice identifying phases from scenarios
- [ ] Understand stakeholder management techniques
- [ ] Know the difference between artifacts and deliverables
- [ ] Review governance principles (CRICS for EA principles)
- [ ] Understand Building Blocks (ABB vs SBB)
- [ ] Review gap analysis technique
- [ ] Know the two validation gates (end of A and F)
- [ ] Understand Requirements Management (applies to all phases)
- [ ] Bring 2 pieces of ID to the exam
- [ ] Familiarize yourself with TOGAF Standard document structure (for quick lookup)

---

**Good luck with your TOGAF L2 Practitioner certification! 🎓**
