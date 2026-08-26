# SalvageGraph

### AI-Powered Construction Material Recovery & Reuse System

> **Turning construction surplus into searchable, traceable, and intelligently reusable resources.**







\

---

## Overview

**SalvageGraph** is a full-stack AI/ML system designed to identify potentially reusable construction materials, characterize their type and visible condition, create structured digital material records, and intelligently connect recovered material supply with material demand from other construction projects.

The system is designed to go beyond conventional construction-waste listings or keyword-based marketplaces.

Instead of simply asking:

> **"Is this material available?"**

SalvageGraph asks:

> **"Is this recovered material a suitable, practical, economical, and environmentally beneficial match for this specific project?"**

The recommendation process considers multiple factors including:

* Material compatibility
* Material dimensions
* Quantity
* Visible condition
* Age and previous usage
* Project requirements
* Geographic distance
* Transportation cost
* Required deadline
* Intended application
* Estimated economic savings
* Estimated environmental benefit

This multi-constraint approach is the central intelligence layer of SalvageGraph.

---

# Why SalvageGraph?

Construction projects frequently generate surplus or recovered materials that may still have functional or economic value. However, information about those materials is often fragmented across projects, warehouses, documents, and people.

At the same time, another construction project may need essentially the same material and purchase it from a conventional supplier because the available recovered resource cannot be efficiently discovered or evaluated.

This creates an **information and coordination gap**.

Traditional workflow:

```text
Construction Project
        ↓
Unused / Surplus Material
        ↓
Storage / Disposal
        ↓
New Project Purchases New Material
```

SalvageGraph proposes a circular digital workflow:

```text
Project A
   ↓
Surplus / Recovered Material
   ↓
AI Characterization
   ↓
Digital Material Passport
   ↓
Material Inventory
   ↓
Project Demand
   ↓
Candidate Matching
   ↓
Suitability + Logistics + Cost Analysis
   ↓
Reuse Recommendation
   ↓
Human Verification
   ↓
Project B
```

The project is positioned around solving the information and decision-making problem rather than simply creating another material marketplace.

---

# Core Research Positioning

SalvageGraph does **not** claim to invent AI-based construction-material reuse or AI matchmaking.

Existing research already explores:

* Construction-material identification
* Computer vision
* Defect detection
* Digital material passports
* Material tracking
* AI-assisted reuse
* Reuse optimization
* Supply-demand matchmaking

The research opportunity addressed by SalvageGraph is the **integration** of these capabilities into an explainable, end-to-end decision system.

The intended contribution is:

```text
Material Characterization
          +
Condition Assessment
          +
Project-Demand Matching
          +
Spatial Constraints
          +
Logistics
          +
Economic Feasibility
          +
Environmental Considerations
          ↓
Explainable Reuse Recommendation
```

This positioning is important because claiming simply "AI for construction-material reuse" would not accurately represent the existing research landscape.

---

# Key Features

## 1. AI-Based Material Characterization

Users can register recovered construction materials using images and structured information.

The computer-vision pipeline is designed to support:

```text
Image
  ↓
Preprocessing
  ↓
Object Detection
  ↓
Material Identification
  ↓
Defect Detection
  ↓
Condition Features
  ↓
Structured Material Record
```

The initial MVP scope focuses on:

* Tiles
* Bricks
* Pipes

Potential future expansion includes:

* Steel sections
* Timber

---

## 2. Visible Condition Assessment

The system is designed to identify visible defects and derive condition-related features from images.

Potential detectable visual characteristics include:

* Cracks
* Stains
* Spalling
* Surface irregularities
* Other visible defects

A YOLO-based computer-vision architecture is proposed for this component.

However, SalvageGraph intentionally distinguishes:

> **AI-based visual condition estimation**

from:

> **Professional engineering certification**

The system should never interpret an image-based prediction as proof that a structural component is safe for engineering use. Professional inspection and testing remain necessary where applicable.

---

# 3. Digital Material Passport

Every recovered material can receive a unique digital identity.

Example:

```text
Material ID:        SG-TILE-00091
Material:           Ceramic Tile
Dimensions:         600 × 600 mm
Quantity:           205 m²
Condition:          Good
Source Project:     P12
Current Location:   Warehouse W03
Registered:         23 Aug 2026
AI Confidence:      94%
```

A QR code can connect the physical material to its digital record.

```text
Physical Material
       ↓
     QR Code
       ↓
Digital Material Passport
       ↓
Material Information
       ↓
Lifecycle / Reuse History
```

The passport is intended to preserve:

* Identity
* Material properties
* Condition
* Origin
* Quantity
* Location
* Previous usage
* Reuse possibilities
* Lifecycle status
* Verification information

---

# 4. Project Demand Registration

Construction projects can define material requirements such as:

```text
Project:
P-102

Material:
Ceramic Tile

Dimensions:
600 × 600 mm

Required Quantity:
180 m²

Minimum Condition:
Good

Required By:
15 September

Location:
Site B

Budget:
₹50,000
```

The system uses these requirements to identify potentially suitable recovered materials.

---

# 5. Intelligent Candidate Matching

SalvageGraph uses a two-stage matching strategy.

### Stage 1 — Hard Filtering

Clearly unsuitable materials are removed first.

```text
Required: Ceramic Tile

Candidate A → Ceramic Tile ✓
Candidate B → Brick         ✗
Candidate C → Ceramic Tile ✓
Candidate D → Pipe          ✗
```

### Stage 2 — Suitability Ranking

Remaining candidates are ranked according to multiple characteristics.

Possible model inputs include:

* Material similarity
* Dimension similarity
* Quantity ratio
* Condition score
* Age
* Distance
* Transportation cost
* Deadline difference
* Application compatibility
* Estimated savings

Output:

```text
Suitability Score: 0–100
```

---

# 6. Explainable Recommendations

SalvageGraph is designed to avoid producing a meaningless output such as:

```text
Match = 92%
```

Instead, the system should explain **why** a material was recommended.

Example:

```text
Recommended Match
──────────────────────────────
Project: Project B

✓ Material type compatible
✓ Dimensions compatible
✓ Quantity sufficient
✓ Condition acceptable
✓ Distance within acceptable range
✓ Deadline achievable
✓ Estimated transportation considered
✓ Economic benefit identified

Estimated Saving: ₹30,200

Overall Suitability: 92%
```

This makes the recommendation more useful to human decision-makers and more defensible as an AI-assisted decision system.

---

# 7. Geospatial & Logistics Analysis

Physical distance can determine whether reuse is actually practical.

Two materials may be technically compatible but economically unsuitable if transportation costs become excessive.

The proposed workflow is:

```text
Material Location
       +
Project Location
       ↓
Distance Calculation
       ↓
Transport Estimation
       ↓
Economic Feasibility
```

The proposed geospatial technology includes:

* PostgreSQL
* PostGIS
* Optional OpenStreetMap-based routing/distance information

---

# 8. Economic Feasibility

The system can estimate the financial value of reuse.

Conceptually:

```text
New Material Cost
       -
Recovered Material Cost
       -
Transportation Cost
       -
Handling Cost
       =
Estimated Net Saving
```

Example:

```text
New Purchase       = ₹100,000
Recovered Material = ₹30,000
Transportation     = ₹12,000
Handling           = ₹5,000

Estimated Saving   = ₹53,000
```

The actual valuation model depends on the quality and availability of project data and should therefore be treated as an estimate rather than a guaranteed financial outcome.

---

# 9. Environmental Benefit Estimation

The system is designed to estimate potential environmental benefits such as:

* Material diverted from disposal
* Virgin-material replacement
* Transportation impact
* Approximate avoided emissions

These values should be treated as **estimated environmental benefits**, not formal lifecycle-assessment results unless a validated LCA methodology is implemented.

```text
Recovered Material
        ↓
Virgin Material Avoided
        ↓
Potential Waste Reduction
        ↓
Estimated Environmental Benefit
```

---

# 10. Allocation Optimization

A single recovered material may potentially satisfy multiple project requirements.

For example:

```text
             Material A
                 │
        ┌────────┼────────┐
        ↓        ↓        ↓
       P1       P2       P3
```

The optimization layer is intended to determine the allocation that maximizes reuse value while respecting:

* Quantity
* Compatibility
* Deadlines
* Transportation
* Project requirements

The initial approach can use weighted scoring, with constraint optimization considered as a later enhancement. OR-Tools is identified as a possible optimization technology.

---

# System Architecture

```text
┌──────────────────────────────────────────────────────────┐
│                    SALVAGEGRAPH                           │
└──────────────────────────────────────────────────────────┘

        MATERIAL SUPPLY                 PROJECT DEMAND
              │                               │
              ↓                               ↓
     Material Registration          Requirement Registration
              │                               │
              ↓                               ↓
       Image / Data Upload             Requirement Parser
              │                               │
              ↓                               ↓
      ┌─────────────────┐              Candidate Retrieval
      │ AI Characterizer│                     │
      └────────┬────────┘                     ↓
               │                       Compatibility Model
        ┌──────┴──────┐                       │
        ↓             ↓                       ↓
 Material Type   Condition/Defect     Multi-Constraint Scoring
        │             │                       │
        └──────┬──────┘          ┌────────────┼────────────┐
               ↓                  ↓            ↓            ↓
      Material Passport       Distance     Transport    Deadline
               │                  │            │            │
               └──────────────────┼────────────┼────────────┘
                                  ↓
                          Economic Analysis
                                  ↓
                       Environmental Analysis
                                  ↓
                       Ranked Recommendations
                                  ↓
                         Human Verification
                                  ↓
                           Reuse Decision
```

This workflow follows the methodology defined in the project documentation.

---

# Technology Stack

## Frontend

| Technology    | Purpose                                   |
| ------------- | ----------------------------------------- |
| React         | User interface                            |
| TypeScript    | Type-safe frontend development            |
| Tailwind CSS  | UI styling                                |
| Recharts      | Data visualization                        |
| Map Interface | Geographic material/project visualization |

## Backend

| Technology | Purpose                          |
| ---------- | -------------------------------- |
| Python     | Core backend and ML ecosystem    |
| FastAPI    | REST API layer                   |
| REST APIs  | Frontend/backend communication   |
| WebSocket  | Optional real-time communication |

## Database

| Technology | Purpose                                 |
| ---------- | --------------------------------------- |
| PostgreSQL | Core relational database                |
| PostGIS    | Geospatial data and distance operations |
| pgvector   | Optional semantic similarity/search     |

## AI / Machine Learning

| Technology         | Purpose                         |
| ------------------ | ------------------------------- |
| PyTorch            | Deep-learning framework         |
| Ultralytics YOLO   | Material and defect detection   |
| Scikit-learn       | Classical machine learning      |
| XGBoost / LightGBM | Suitability ranking             |
| Python             | ML pipeline and experimentation |

## Optimization

| Technology | Purpose                                |
| ---------- | -------------------------------------- |
| OR-Tools   | Constraint optimization and allocation |

## Deployment

| Technology     | Purpose                        |
| -------------- | ------------------------------ |
| Docker         | Application containerization   |
| Docker Compose | Multi-service local deployment |

The proposed technology architecture is documented in the project specification.

---

# Data Model

A simplified conceptual relationship model is:

```text
PROJECT
   │
   ├── produces ──────────→ MATERIAL
   │                           │
   │                           ├── belongs to → MATERIAL TYPE
   │                           │
   │                           ├── has → CONDITION
   │                           │
   │                           ├── stored at → WAREHOUSE
   │                           │
   │                           └── candidate for → PROJECT
   │
   └── requires → MATERIAL REQUIREMENT
```

The "Graph" concept represents relationships and lifecycle connections rather than requiring a graph database by default.

PostgreSQL relational relationships are considered sufficient for the initial system; a graph database such as Neo4j should only be introduced if it provides a measurable analytical advantage.

---

# End-to-End Workflow

### Step 1 — Register Material

A user records:

* Image
* Material type, if known
* Quantity
* Dimensions
* Location
* Source
* Age

### Step 2 — AI Characterization

The image is processed through the computer-vision pipeline.

```text
Image
 ↓
Preprocessing
 ↓
YOLO
 ↓
Material Detection
 ↓
Defect Detection
 ↓
Condition Features
```

### Step 3 — Generate Material Passport

The system creates:

* Material ID
* Type
* Subtype
* Quantity
* Dimensions
* Condition
* Image
* Location
* Source
* History
* AI confidence
* QR code

### Step 4 — Register Project Demand

A project manager specifies the required material and constraints.

### Step 5 — Candidate Retrieval

Impossible candidates are removed through hard filtering.

### Step 6 — Suitability Ranking

The remaining candidates are ranked using compatibility, condition, quantity, location, logistics, deadline and economic factors.

### Step 7 — Optimization

If multiple projects compete for the same material, the allocation can be optimized.

### Step 8 — Economic Analysis

The system estimates potential net savings.

### Step 9 — Environmental Analysis

The system estimates potential resource and waste benefits.

### Step 10 — Human Verification

A qualified human reviews the recommendation before reuse.

```text
AI Recommendation
       ↓
Human Review
       ↓
┌──────┼────────────┐
↓      ↓            ↓
Approve Reject  Inspect Further
```

The final decision remains human-controlled.

---

# AI & Machine Learning Strategy

## Material Detection

The proposed vision system can use a YOLO-based detector for:

```text
Tiles
Bricks
Pipes
Steel Sections
Visible Defects
```

The model should be trained or fine-tuned using a carefully labelled dataset appropriate to the target material classes.

---

## Suitability Model

A suitability model can incorporate:

```text
Material Compatibility
Dimension Similarity
Quantity Availability
Condition
Age
Distance
Transportation Cost
Deadline
Application Compatibility
Estimated Savings
```

A conceptual score can be represented as:

```text
Suitability = f(
    compatibility,
    dimensions,
    quantity,
    condition,
    distance,
    transport,
    deadline,
    economics
)
```

An example scoring framework from the research documentation is:

| Factor                 | Example Weight |
| ---------------------- | -------------: |
| Material Compatibility |            30% |
| Condition              |            20% |
| Quantity               |            10% |
| Distance               |            10% |
| Deadline               |            10% |
| Transport Cost         |            10% |
| Economic Benefit       |             5% |
| Environmental Benefit  |             5% |
| **Total**              |       **100%** |

These weights are **illustrative**, not validated production weights. The documentation explicitly recommends learning or experimentally optimizing the final weights rather than presenting arbitrary weights as scientifically established.

---

# Research & Academic Foundation

SalvageGraph builds upon research covering several parts of the circular-construction ecosystem.

### Byers et al. (2024)

**From Research to Practice: A Review on Technologies for Addressing the Information Gap for Building Material Reuse in Circular Construction**

Provides the information-architecture foundation for material passports and lifecycle information.

### De Wolf et al. (2024)

**D5 Digital Circular Workflow: Five Digital Steps Towards Matchmaking for Material Reuse in Construction**

Provides the broader digital circular workflow:

```text
Detection
   ↓
Disassembly
   ↓
Distribution
   ↓
Design
   ↓
Deployment
```

SalvageGraph focuses particularly on the supply-demand matchmaking and decision-intelligence layer.

### Gordon & De Wolf (2024)

**Optimisation Goals for Efficient Construction from Reused Materials Towards a Circular Built Environment**

Supports the multi-factor optimization perspective rather than simple material-type matching.

### Zboinska & Göbel (2025)

**Digital Tool Integrations for Architectural Reuse of Salvaged Building Materials**

Supports the use of computer vision, machine learning and digital tools for irregular salvaged-material reuse.

### Dai et al. (2024)

**Component-Level Residential Building Material Stock Characterization Using Computer Vision Techniques**

Supports the use of computer vision for construction-material characterization and inventory estimation.

### HaitherAli et al. (2026)

**Characterisation and Evaluation of Construction and Demolition Waste for Sustainable Reuse**

Highlights the importance of physical properties, quality, impurities and economic considerations when evaluating reuse suitability.

### Zhuang & Jiang (2026)

**Deep Learning Approaches for Automated Defect Detection and Quality Control in Construction Materials**

Provides relevant evidence for YOLO-based construction-material defect detection.

### Byers & De Wolf (2023)

**QR Code-Based Material Passports for Component Reuse Across Life Cycle Stages in Small-Scale Construction**

Supports the physical-to-digital material-passport concept.

### Costa, Hoolahan & Charef (2025)

**Eight Recommendations to Adopt Materials Passports and Accelerate Material Reuse in Construction**

Supports structured lifecycle information and interoperability for material passports.

### Wilson et al. (2023)

**Tracking Material Reuse Across Construction Supply Chains**

Supports provenance, lifecycle tracking and material relationships.

### Moya-Jiménez et al. (2026)

**Application of Computer Vision and Parametric Design Algorithms for the Reuse of Construction Materials**

Demonstrates how AI-based material classification can participate in broader reuse workflows.

---

# Project Objectives

SalvageGraph is designed around the following objectives:

1. Build a digital inventory for recovered construction materials.
2. Develop computer-vision-based material identification.
3. Develop AI-assisted visible-condition assessment.
4. Develop material-to-project compatibility analysis.
5. Develop multi-constraint suitability scoring.
6. Integrate geographic and transportation constraints.
7. Estimate economic feasibility.
8. Generate explainable ranked recommendations.
9. Maintain digital material passports and lifecycle history.
10. Evaluate whether intelligent matching improves matching quality and reduces manual search effort compared with simpler approaches.

---

# MVP Scope

The initial MVP focuses on **non-hazardous reusable construction materials**.

### Supported MVP Materials

* Ceramic tiles
* Bricks
* Pipes

### Potential Future Materials

* Steel sections
* Timber

The system is intentionally scoped so that advanced technologies such as robotics, 3D printing, and blockchain are not required for the initial MVP.

---

# Project Status

**Current Status: Research / MVP Development**

The project architecture and methodology are defined around:

* Full-stack web application
* AI material characterization
* Visible-condition assessment
* Digital material passports
* Project-demand matching
* Multi-constraint suitability scoring
* Geospatial analysis
* Economic feasibility
* Environmental estimation
* Human verification
* Future optimization

The project documentation identifies software feasibility as high, while identifying **data availability and labelled real-world material data as one of the major technical risks**.

---

# Dataset Strategy

A major challenge is the lack of a single ready-made dataset containing everything required by SalvageGraph.

The proposed data strategy combines:

```text
Public Research Data
        +
Self-Collected Images
        +
Controlled Condition Labels
        +
Synthetic Project-Demand Data
        ↓
SalvageGraph Dataset
```

This approach allows the system to develop material detection, condition estimation and project-matching components while clearly documenting how synthetic or self-collected data are generated.

The dataset-generation methodology should be documented carefully for academic reproducibility.

---

# Evaluation Strategy

The system should be evaluated at multiple levels rather than using a single "AI accuracy" number.

## Computer Vision

Potential metrics:

* Precision
* Recall
* F1-score
* mAP
* Detection confidence
* Inference time

## Matching System

Potential evaluation dimensions:

* Top-K recommendation quality
* Matching accuracy
* Suitability ranking quality
* False-positive recommendations
* Constraint satisfaction
* Human acceptance rate

## Operational Evaluation

The system should also evaluate:

* Reduction in manual search effort
* Time required to identify suitable materials
* Economic feasibility
* Quantity of material successfully matched
* Transportation implications

The project's stated objective is to compare intelligent matching against simpler matching approaches rather than assuming that AI automatically performs better.

---

# Limitations & Responsible AI

SalvageGraph is an **AI-assisted decision-support system**, not an autonomous engineering authority.

### Important limitations

#### Visual condition is not engineering certification

A model can identify visible defects, but visual inspection alone cannot establish structural safety.

#### Suitability scores are recommendations

A score such as `92%` represents model-based suitability, not a guarantee that reuse is safe, legal, or economically optimal.

#### Environmental values are estimates

Environmental benefits should not be represented as formal carbon accounting unless a validated LCA methodology is implemented.

#### Dataset quality affects model quality

Poorly labelled, biased, or insufficient data can produce unreliable recommendations.

#### Human verification is mandatory

Final reuse decisions should consider:

* Material condition
* Engineering requirements
* Quantity
* Cost
* Transportation
* Applicable standards
* Professional inspection where necessary

These safeguards are explicitly incorporated into the project methodology.

---

# Security & Data Considerations

A production implementation should protect:

* User accounts
* Project information
* Material records
* Uploaded images
* Location information
* Commercial cost information
* Material lifecycle history
* AI-generated recommendations

Future implementations should also consider:

* Authentication and authorization
* Role-based access control
* Secure file uploads
* API validation
* Database access controls
* Audit logging
* Rate limiting
* Secure environment variables
* Data backup and recovery

These are engineering requirements for a production deployment and should not be interpreted as claims that every item is already implemented.

---

# Deployment Architecture

The proposed deployment model uses containerized services.

```text
                   ┌─────────────────┐
                   │   Web Client     │
                   │ React + TS       │
                   └────────┬────────┘
                            │
                            ↓
                   ┌─────────────────┐
                   │    FastAPI      │
                   │    REST API     │
                   └───────┬─────────┘
                           │
             ┌─────────────┼──────────────┐
             ↓             ↓              ↓
       PostgreSQL       AI/ML         Geospatial
       + PostGIS        Services       Services
             │             │              │
             └─────────────┼──────────────┘
                           ↓
                    Recommendation
                       Engine

              Docker / Docker Compose
```

The proposed stack identifies Docker and Docker Compose for deployment.

---

# Repository Structure

The following structure is recommended for the implementation:

```text
salvagegraph/
│
├── frontend/
│   ├── public/
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── layouts/
│       ├── services/
│       ├── hooks/
│       ├── types/
│       ├── utils/
│       └── App.tsx
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   ├── core/
│   │   └── main.py
│   │
│   └── tests/
│
├── ai/
│   ├── datasets/
│   ├── detection/
│   ├── condition/
│   ├── matching/
│   ├── optimization/
│   ├── training/
│   └── inference/
│
├── database/
│   ├── migrations/
│   └── seeds/
│
├── docs/
│   ├── architecture/
│   ├── research/
│   ├── api/
│   └── diagrams/
│
├── notebooks/
│
├── scripts/
│
├── docker/
│
├── .env.example
├── docker-compose.yml
├── README.md
├── LICENSE
└── .gitignore
```

> This is a recommended repository organization derived from the documented architecture; it should be adjusted to match the actual implementation.

---

# Development Roadmap

## Phase 1 — Research & Requirements

* Literature review
* Problem definition
* Requirement analysis
* MVP scope definition

## Phase 2 — Dataset

* Collect material images
* Define material classes
* Label visible defects
* Define condition categories
* Create project-demand dataset
* Generate controlled synthetic demand scenarios

## Phase 3 — Backend & Database

* PostgreSQL schema
* PostGIS integration
* Material records
* Project records
* Material passports
* Lifecycle history
* API layer

## Phase 4 — Computer Vision

* Image preprocessing
* Material detection
* Defect detection
* Condition feature extraction
* Model evaluation

## Phase 5 — Matching Engine

* Hard filtering
* Compatibility scoring
* Suitability ranking
* Distance integration
* Deadline constraints
* Economic analysis

## Phase 6 — Optimization

* Multi-project allocation
* Quantity constraints
* Logistics constraints
* Deadline constraints
* Reuse-value optimization

## Phase 7 — Frontend

* Dashboard
* Material inventory
* Material registration
* Material passport
* Project requirements
* Matching results
* Maps
* Analytics

## Phase 8 — Integration

```text
Frontend
   ↓
Backend API
   ↓
Database
   ↓
AI Services
   ↓
Matching Engine
   ↓
Optimization
   ↓
Recommendation
```

## Phase 9 — Evaluation

* Model evaluation
* Matching evaluation
* Baseline comparison
* User workflow evaluation
* Economic analysis
* Documentation

The project documentation outlines an approximately 24-week development sequence covering these stages.

---

# Future Scope

Potential future extensions include:

### Advanced Computer Vision

* Better material classification
* Multi-view material inspection
* 3D reconstruction
* Photogrammetry
* Automated dimension estimation

### Intelligent Matching

* Semantic material similarity
* Learned suitability models
* Context-aware project requirements
* Improved ranking algorithms

### Optimization

* Advanced constraint optimization
* Multi-project resource allocation
* Supply-chain optimization

### Digital Infrastructure

* Standardized material-passport APIs
* Interoperability with construction platforms
* Lifecycle tracking across organizations
* Advanced provenance systems

### Expanded Material Classes

* Steel
* Timber
* Glass
* Stone
* Concrete components
* Other non-hazardous reusable materials

### Environmental Intelligence

* Formal LCA integration
* Material-specific embodied-carbon databases
* More accurate transport emissions
* Circularity indicators

### Graph Analytics

A dedicated graph database such as Neo4j may be investigated if graph-based queries provide measurable analytical benefits beyond the PostgreSQL relational implementation.

---

# What Makes SalvageGraph Different?

SalvageGraph is not intended to be merely:

```text
Construction Marketplace
```

or:

```text
Material Inventory System
```

or:

```text
Computer Vision Classifier
```

or:

```text
Material Passport Database
```

Its intended architecture combines these capabilities into a decision-support pipeline:

```text
                    SalvageGraph
                         │
       ┌─────────────────┼──────────────────┐
       ↓                 ↓                  ↓
Material Recovery   Project Demand     Lifecycle Data
       │                 │                  │
       ↓                 ↓                  ↓
AI Characterization  Requirement Data   Material Passport
       │                 │                  │
       └─────────────────┼──────────────────┘
                         ↓
                 Candidate Retrieval
                         ↓
                Compatibility Analysis
                         ↓
              Multi-Constraint Ranking
                         ↓
          ┌──────────────┼──────────────┐
          ↓              ↓              ↓
      Geography       Economics     Environment
          │              │              │
          └──────────────┼──────────────┘
                         ↓
                  Recommendation
                         ↓
                  Human Verification
                         ↓
                    Reuse Decision
```

That integrated decision-intelligence layer is the core research direction of the project.

---

# Project Outcomes

The intended MVP outcome is a system capable of:

* Registering recovered construction materials
* Identifying probable material classes
* Detecting visible defects
* Estimating visible condition
* Creating persistent digital material passports
* Connecting material supply with project demand
* Filtering incompatible candidates
* Ranking suitable candidates
* Considering geographic distance
* Estimating transportation implications
* Estimating economic benefit
* Estimating environmental benefit
* Providing explainable recommendations
* Supporting human verification before reuse

---

# Technical Feasibility

| Area                                 | Assessment             |
| ------------------------------------ | ---------------------- |
| Full-stack development               | High                   |
| Database architecture                | High                   |
| REST API                             | High                   |
| Computer vision                      | Medium–High            |
| Defect detection                     | Medium–High            |
| Matching engine                      | Medium–High            |
| Geospatial analysis                  | High                   |
| Optimization                         | Medium                 |
| Dataset availability                 | Medium / Major Risk    |
| Engineering certification through AI | **Not a project goal** |

The principal technical risk is not whether the software stack exists. The larger challenge is obtaining sufficient high-quality labelled data for realistic material characterization and condition-aware matching.

---

# Responsible Use

SalvageGraph should be treated as a **decision-support platform**.

It should not:

* Certify structural safety
* Replace professional engineering inspection
* Guarantee economic savings
* Guarantee successful material reuse
* Produce formal environmental LCA results without validated methodology
* Automatically authorize construction use

The final reuse decision should remain subject to appropriate human and professional verification.

---

# Contributing

Contributions are welcome as the project evolves.

Recommended contribution workflow:

```text
1. Fork the repository
2. Create a feature branch
3. Implement the change
4. Add or update tests
5. Document the change
6. Commit using a clear message
7. Open a Pull Request
```

For research-related contributions, include:

* Dataset source
* Experimental methodology
* Model configuration
* Evaluation metrics
* Reproducibility information

---

# Academic & Research Use

SalvageGraph is intended to serve as both a software engineering project and an applied AI/ML research system for circular construction.

Research areas include:

* Circular economy
* Construction and demolition waste
* Construction-material reuse
* Computer vision
* Machine learning
* Digital material passports
* Geospatial intelligence
* Optimization
* Decision-support systems
* Sustainable construction
* AI-assisted resource allocation

---

# Disclaimer

SalvageGraph is an experimental/research-oriented AI-assisted system.

Predictions, suitability scores, cost estimates, transportation estimates, and environmental estimates are model-based outputs and should not be interpreted as professional engineering certification, guaranteed financial outcomes, or formal environmental assessments.

Human verification remains an essential part of the proposed workflow.

---

# License

This project is currently intended for academic and research development.

The final open-source license should be selected and added to the repository before public distribution.

---

# Project Name

**SalvageGraph**

### Full Title

> **SalvageGraph: An AI-Powered Construction Material Recovery and Project-to-Project Reuse Intelligence System**

### Core Idea

> **Recover → Characterize → Passport → Match → Evaluate → Verify → Reuse**

---

## Built Around a Simple Principle

> **A material is not waste simply because one construction project no longer needs it.**
>
> **Its value depends on whether another project can discover it, evaluate it, and reuse it intelligently.**

---

### Research Foundation

The project architecture and research positioning are based on the supplied SalvageGraph project documentation, including work on digital circular workflows, material passports, computer vision, construction-material characterization, defect detection, optimization, and material reuse.
