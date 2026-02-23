# 01 — Phonology

SUBIT‑Lingua uses a deliberately minimal and highly distinct phonological system.  
Its purpose is not to imitate natural languages, but to provide a **structural, unambiguous, and machine‑readable interface** that maps directly onto the SUBIT‑RFC architecture.

The phonology is built from:

- **3 consonants** — representing the three SUBIT axes  
- **4 vowels** — representing the four SUBIT bigrams  
- **12 base syllables** — forming the phonological crystal of the language

This chapter defines the phonological inventory, articulatory motivation, structural mapping, and combinatorial rules.

---

## 1. Consonant Inventory (3 axes)

SUBIT‑Lingua uses exactly **three consonants**, each corresponding to one of the three SUBIT axes: WHO, WHERE, WHEN.

| Consonant | Axis  | Articulation | Type | Structural Role |
|-----------|-------|--------------|------|-----------------|
| **K** | WHO | velar | voiceless stop | agent, subject, core |
| **T** | WHERE | alveolar | voiceless stop | space, structure, boundary |
| **M** | WHEN | bilabial | nasal | time, phase, continuity |

### 1.1 Motivation

The consonants were selected according to four criteria:

1. **Maximal acoustic contrast**  
   - K (back stop), T (front stop), M (nasal) form a stable articulatory triangle.

2. **Universal pronounceability**  
   - All three appear in the majority of world languages.

3. **Structural isomorphism**  
   - Each consonant corresponds to a SUBIT axis:
     - K → WHO  
     - T → WHERE  
     - M → WHEN  

4. **Machine‑readability**  
   - Distinct spectral signatures simplify ASR/TTS processing.

---

## 2. Vowel Inventory (4 bigrams)

SUBIT‑Lingua uses **four vowels**, each representing one of the four SUBIT bigrams (00, 01, 10, 11).

| Vowel | Bigram | Quality | Structural Role |
|-------|--------|---------|-----------------|
| **A** | 00 | open front | emptiness, potential, origin |
| **E** | 01 | mid front | form, boundary, structure |
| **O** | 10 | mid back | depth, source, root |
| **U** | 11 | close back | energy, intensity, realization |

### 2.1 Motivation

The vowels were chosen to maximize:

- **phonetic clarity** (A–E–O–U are globally stable)  
- **structural mapping** (each vowel = SUBIT bigram)  
- **semantic transparency** (open ↔ empty, closed ↔ intense)

---

## 3. Syllable Structure

SUBIT‑Lingua uses a single canonical syllable pattern:

```
C V
```

Where:

- **C** ∈ {K, T, M}  
- **V** ∈ {A, E, O, U}

This yields **12 base syllables**.

---

## 4. The 12 Base Syllables

These syllables form the **phonological crystal** of SUBIT‑Lingua.  
Each syllable is a direct mapping of:

```
[Axis] + [Bigram]
```

| Axis | A (00) | E (01) | O (10) | U (11) |
|------|--------|--------|--------|--------|
| WHO (K) | **KA** | **KE** | **KO** | **KU** |
| WHERE (T) | **TA** | **TE** | **TO** | **TU** |
| WHEN (M) | **MA** | **ME** | **MO** | **MU** |

These 12 syllables are the **atomic units** of the language.  
All morphology, lexicon, and syntax derive from them.

---

## 5. Phonotactic Rules

### 5.1 Allowed structures

- **Monosyllabic roots:** CV  
- **Doubled forms:** CV‑CV  
- **Trisyllabic structured forms:** CV‑CV‑CV  
- **Compounds:** concatenation of valid forms

### 5.2 Forbidden structures

To preserve regularity:

- no consonant clusters  
- no diphthongs  
- no codas  
- no tones  
- no stress distinctions  

SUBIT‑Lingua is intentionally **flat and regular**.

---

## 6. Prosody

SUBIT‑Lingua uses:

- **even stress**  
- **no pitch distinctions**  
- **no length contrasts**

Prosody is intentionally minimized to ensure:

- cross‑linguistic accessibility  
- ease of synthesis  
- structural clarity

---

## 7. Structural Mapping Summary

| Layer | Element | Count | Maps To |
|-------|---------|-------|---------|
| Phonology | 3 consonants | 3 | SUBIT axes |
| Phonology | 4 vowels | 4 | SUBIT bigrams |
| Syllables | 12 CV forms | 12 | SUBIT atomic states |
| Morphology | 48 doubled forms | 48 | SUBIT extended states |
| Morphology | 64 structured forms | 64 | SUBIT cube |

SUBIT‑Lingua is therefore **phonologically isomorphic** to the SUBIT‑64 architecture.

---
