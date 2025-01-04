
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
  **Explanation:** This represents a statement that Germany has Berlin as its capital.

### Rule: Use Period (`.`) to End Each Triple
- **Why:** Indicates the end of a statement.

---

## **2. URIs**

### Rule: Enclose URIs in `< >`
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#state> <http://example.org/#Bavaria> .
  ```
  **Explanation:** This states that Bavaria is a state of Germany.

---

## **3. Syntactic Sugar**

### Rule: Use Semicolon (`;`) to Repeat a Subject
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#capital> <http://example.org/#Berlin> ;
      <http://example.org/#state> <http://example.org/#Bavaria> .
  ```
  **Explanation:** This combines two statements about Germany: its capital is Berlin, and its state is Bavaria.

### Rule: Use Comma (`,`) to Repeat Subject-Predicate Combinations
- **Example:**
  ```turtle
  <http://example.org/#Germany> <http://example.org/#state> <http://example.org/#Berlin> ,
      <http://example.org/#Bavaria> .
  ```
  **Explanation:** This states that Germany has two states: Berlin and Bavaria.

---

## **4. CURIEs (Compact URIs)**

### Rule: Define Prefixes Using `@prefix`
- **Example:**
  ```turtle
  @prefix ex: <http://example.org/#> .
  ex:Germany ex:capital ex:Berlin .
  ```
  **Explanation:** Using prefixes (`ex:`) makes the graph cleaner and easier to read.

---

## **5. Literals**

### Rule: Use Double Quotes (`""`) for String Values
- **Example:**
  ```turtle
  ex:Germany ex:name "Deutschland" .
  ```
  **Explanation:** This specifies that Germany's name is "Deutschland."

### Rule: Specify Data Types with `^^`
- **Example:**
  ```turtle
  ex:Germany ex:population "83042235"^^xsd:int .
  ```
  **Explanation:** This indicates that Germany's population is 83,042,235 (an integer).

### Rule: Use Language Tags with `@`
- **Example:**
  ```turtle
  ex:Germany ex:name "Deutschland"@de .
  ex:Germany ex:name "Germany"@en .
  ```
  **Explanation:** This specifies Germany's name in German and English.

**Note:** `xsd` is a namespace used to define standard data types like integers, dates, and strings.

---

## **6. Blank Nodes**

### Rule: Use `_:` for Anonymous Nodes
- **Example:**
  ```turtle
  ex:me ex:knows _:1 .
  _:1 rdf:type ex:Professor .
  ```
  **Explanation:** Blank nodes represent resources without a URI, like an unnamed professor that "I" know.

### Rule: Use Brackets (`[ ]`) for Inline Blank Nodes
- **Example:**
  ```turtle
  ex:student ex:grading [
      ex:grade "1.0" ;
      ex:grader ex:Professor
  ] .
  ```
  **Explanation:** Inline blank nodes make data more compact and readable, useful for details like grades and graders.

**Why Use Blank Nodes?**
- **When to Use:** For entities without identifiers (e.g., unnamed individuals or temporary information).
- **Benefits:** Simplifies data representation and avoids creating unnecessary URIs for transient or secondary data.

---

## **7. Tips for Clean Turtle Documents**
- Use prefixes to simplify repeated URIs.
- Use syntactic sugar (`;` and `,`) to reduce redundancy.
- Validate RDF graphs with tools to ensure correctness.

---
