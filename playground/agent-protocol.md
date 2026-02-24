# SUBIT‑Lingua — Agent Communication Protocol

This document defines how agents communicate using SUBIT‑Lingua as a structural,
minimal, and deterministic interface. SUBIT‑Lingua provides a phonological and
morphological layer over the SUBIT‑RFC state model, enabling agents to exchange
states, transitions, and structural intentions in a compact, interpretable form.

The protocol is designed for:
- agent‑to‑agent communication  
- agent‑to‑system communication  
- structural reasoning  
- state reporting  
- process description  
- interactive modulation  

---

# 1. Message Types

Agents communicate using four canonical message types:

### 1.1 STATE
A single structured form (CV‑CV‑CV) representing a SUBIT‑64 cube state.

Example:
```
KA-TE-MO
```

### 1.2 MODULATION
A doubled form (CV‑CV) modifying the previous state.

Example:
```
ME-MO
```

### 1.3 CHAIN
A sequence of units (atomic, doubled, or structured) expressing a process.

Example:
```
KA-TE-MU TA-ME MA-KU-ME
```

### 1.4 QUERY
A request for interpretation, continuation, or transformation.

Example:
```
KA-TE-MO ?
```

---

# 2. Message Structure

A SUBIT‑Lingua agent message has the following canonical structure:

```
<type> <payload> <optional-annotation>
```

### Examples

**State report**
```
STATE KA-TE-ME
```

**Modulation**
```
MOD ME-MO
```

**Chain**
```
CHAIN KA-TA-MA KE-TE-ME KO-TO-MO
```

**Query**
```
QUERY KA-TE-MU neighbors
```

---

# 3. Interpretation Rules

Agents must interpret SUBIT‑Lingua messages according to:

### 3.1 Axis Semantics
- K = WHO  
- T = WHERE  
- M = WHEN  

### 3.2 Bigram Semantics
- A = 00  
- E = 01  
- O = 10  
- U = 11  

### 3.3 Composition
Left‑to‑right:
```
Unit1 → Unit2 → Unit3
```

### 3.4 Stability
Doubled forms with identical vowels (A‑A, E‑E, O‑O, U‑U) represent stable states.

### 3.5 Modulation
Doubled forms with different vowels represent transitions.

---

# 4. Agent Behaviors

Agents must support the following behaviors:

### 4.1 State Description
Given a structured form, the agent returns:
- axis values  
- bigram values  
- structural interpretation  

Example:
```
IN: STATE KE-TO-ME
OUT: WHO(01) WHERE(10) WHEN(01)
```

---

### 4.2 Neighbor Discovery
Given a structured form, the agent returns adjacent states (Hamming distance 1).

Example:
```
IN: QUERY KA-TE-MO neighbors
OUT: KA-TE-MA, KA-TE-MU, KA-TA-MO, KA-TU-MO, KE-TE-MO, KO-TE-MO
```

---

### 4.3 Chain Interpretation
Given a compound, the agent returns a structural narrative.

Example:
```
IN: CHAIN KA-TE-MU TA-ME MA-KU-ME
OUT: subject → structured space → peak time → spatial modulation → temporal intensity
```

---

### 4.4 Transformation
Agents must support:

- axis rotation (K→T→M→K)  
- bigram rotation (A→E→O→U→A)  
- position rotation (unit shift)  

Example:
```
IN: QUERY KA-TE-MA rotate axis
OUT: TA-ME-KA
```

---

# 5. Protocol Flow

A typical interaction follows:

### 5.1 Initiation
Agent A sends a STATE or CHAIN.

### 5.2 Interpretation
Agent B interprets and responds with:
- description  
- modulation  
- continuation  

### 5.3 Modulation
Either agent may send a doubled form to shift the state.

### 5.4 Resolution
Interaction ends with:
- stable form  
- completed chain  
- explicit closure  

---

# 6. Error Handling

Agents must respond with structural clarity.

### 6.1 Invalid Form
```
ERROR invalid-form
```

### 6.2 Ambiguous Request
```
ERROR ambiguous
```

### 6.3 Unsupported Operation
```
ERROR unsupported
```

### 6.4 Recovery
Agents may request clarification:
```
QUERY clarify
```

---

# 7. Minimal Examples

### Example 1 — State Inquiry
```
A: STATE KA-TE-MO
B: WHO(00) WHERE(01) WHEN(10)
```

### Example 2 — Modulation
```
A: MOD ME-MO
B: WHEN 01→10 acknowledged
```

### Example 3 — Chain Interpretation
```
A: CHAIN KA-TA-MA KE-TE-ME KO-TO-MO
B: emergence → form → depth
```

### Example 4 — Transformation
```
A: QUERY KA-TE-MA rotate bigram
B: KE-TE-ME
```

---

# 8. Implementation Notes

- All forms must be valid SUBIT‑Lingua morphology.  
- All semantics must be derived from SUBIT‑RFC.  
- No natural‑language interpretation is required.  
- Agents may optionally provide glosses.  
- Chains must preserve left‑to‑right composition.  

---

# Status

This protocol is part of:

**SUBIT‑Lingua v1.1 — Agent Communication Layer**

---
