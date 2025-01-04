
# RDF Basics and Turtle Syntax Rules

This document provides a simplified guide to working with RDF (Resource Description Framework) using the Turtle syntax. It covers the core concepts, rules, and examples.

---

## **1. Turtle Basics**

### Rule: Structure RDF as Triples
- **Format:** `Subject Predicate Object .`
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#capital> <http://example.org/#Berlin> .
  ```

### Rule: Use Period (`.`) to End Each Triple
- **Why:** Indicates the end of a statement.

---

## **2. URIs**

### Rule: Enclose URIs in `< >`
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#state> <http://example.org/#Bavaria> .
  ```

---

## **3. Syntactic Sugar**

### Rule: Use Semicolon (`;`) to Repeat a Subject
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#capital> <http://example.org/#Berlin> ;
      <http://example.org/#state> <http://example.org/#Bavaria> .
  ```

### Rule: Use Comma (`,`) to Repeat Subject-Predicate Combinations
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#state> <http://example.org/#Berlin> ,
      <http://example.org/#Bavaria> .
  ```

---

## **4. CURIEs (Compact URIs)**

### Rule: Define Prefixes Using `@prefix`
- **Example:**
  ```turtle
  @prefix ex: <http://example.org/#> .
  ex:Germany ex:capital ex:Berlin .
  ```

---

## **5. Literals**

### Rule: Use Double Quotes (`""`) for String Values
- **Example:**
  ```turtle
  ex:Germany ex:name "Deutschland" .
  ```

### Rule: Specify Data Types with `^^`
- **Example:**
  ```turtle
  ex:Germany ex:population "83042235"^^xsd:int .
  ```

### Rule: Use Language Tags with `@`
- **Example:**
  ```turtle
  ex:Germany ex:name "Deutschland"@de .
  ex:Germany ex:name "Germany"@en .
  ```

---

## **6. Blank Nodes**

### Rule: Use `_:` for Anonymous Nodes
- **Example:**
  ```turtle
  ex:me ex:knows _:1 .
  _:1 rdf:type ex:Professor .
  ```

### Rule: Use Brackets (`[ ]`) for Inline Blank Nodes
- **Example:**
  ```turtle
  ex:student ex:grading [
      ex:grade "1.0" ;
      ex:grader ex:Professor
  ] .
  ```

---

## **7. Tips for Clean Turtle Documents**
- Use prefixes to simplify repeated URIs.
- Use syntactic sugar (`;` and `,`) to reduce redundancy.
- Validate RDF graphs with tools to ensure correctness.

---
