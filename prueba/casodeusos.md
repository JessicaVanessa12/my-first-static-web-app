# Use Cases Documentation

This document defines the actors, use case descriptions, and the Use Case Diagram for the **TripSplit** application[cite: 2, 5].

---

## 1. Actors Description

| Actor | Description |
| :--- | :--- |
| **Visitor** | A user without an active session; can only sign up or log in[cite: 4]. |
| **Participant** | An authenticated user belonging to a trip who can view and collaborate on it[cite: 4]. |
| **Organizer** | A participant who created the trip and has administrative privileges over the trip and its members[cite: 4]. |

---

## 2. List of Use Cases

| ID | Use Case | Actor | Requirements |
| :--- | :--- | :--- | :--- |
| **CU-01** | Sign up | Visitor | RF-01[cite: 5] |
| **CU-02** | Log in / Log out | Visitor, Participant | RF-02[cite: 5] |
| **CU-03** | Create trip | Participant | RF-03[cite: 5] |
| **CU-04** | Edit or delete trip | Organizer | RF-04[cite: 5] |
| **CU-05** | Add / remove participants | Organizer | RF-05[cite: 5] |
| **CU-06** | View my trips | Participant | RF-06[cite: 6] |
| **CU-07** | Manage itinerary activities | Participant | RF-07, RF-08, RF-09[cite: 6] |
| **CU-08** | Register shared expense | Participant | RF-10, RF-11[cite: 6] |
| **CU-09** | Consult balances and debts | Participant | RF-12[cite: 6] |
| **CU-10** | Register settlement payment | Participant | RF-13[cite: 6] |
| **CU-11** | Manage luggage checklist | Participant | RF-14[cite: 6] |
| **CU-12** | Consult budget and charts | Participant | RF-15, RF-16[cite: 6] |

---

## 3. Use Case Diagram (Mermaid)

```mermaid
graph TD
    subgraph Actors
        Visitor[Visitor]
        Participant[Participant]
        Organizer[Organizer]
    end

    subgraph TripSplit ["TripSplit System"]
        CU01["CU-01: Sign up"]
        CU02["CU-02: Log in / Log out"]
        CU03["CU-03: Create trip"]
        CU04["CU-04: Edit or delete trip"]
        CU05["CU-05: Add / remove participants"]
        CU06["CU-06: View my trips"]
        CU07["CU-07: Manage itinerary activities"]
        CU08["CU-08: Register shared expense"]
        CU09["CU-09: Consult balances and debts"]
        CU10["CU-10: Register settlement payment"]
        CU11["CU-11: Manage luggage checklist"]
        CU12["CU-12: Consult budget and charts"]
    end

    Visitor --> CU01
    Visitor --> CU02

    Participant --> CU02
    Participant --> CU03
    Participant --> CU06
    Participant --> CU07
    Participant --> CU08
    Participant --> CU09
    Participant --> CU10
    Participant --> CU11
    Participant --> CU12

    Organizer --> CU04
    Organizer --> CU05
    
    %% Inheritance: Organizer inherits from Participant
    Organizer -.->|Extends / Inherits| Participant