---
title: Notes on MATH 125, Mathematical Logic
categories: 05-Mathematical-Logic
tags: Notes Ongoing
---

## Introduction

### Main Goals

To develop the foundations for all mathematics.

### Main Topics

Foundations of logic

Formal systsms

Axioms to develop all the mathematics

### Proof

What is a mathematical proof?
  - An argument that uses `logical steps` to show that a concrete `mathematical statement` follows form certain `assumptions`.
  - Proofs are made out of logical steps.
  - But how to be explicit about **which logical steps we are allowed to use**?

`Hilbert's Program (1900)`:
  - **Trying to find a formal system for mathematics where all true statements can be proved in a purely formal and syntactical way**, that only involves manipulating symbols, following certain rules in a purely mechanical way, without having to even know what the symbols mean.

The result is `formal systems`, which consists of 3 parts: 
  - a language,
  - a set of rules,
  - a list of axioms.

Formal systems can:
  - provide a solid foundation for mathematics.
  - be able to study proofs, theorems, and Constructions **as mathematical objects**.
  - play with computers, namely, `computer verification of proof`, `computer assistence for proofs`.

What is a `formal language`?
  - Consists of 2 parts: symbols and grammers
  - Complete.

What are rules?
  - Logical Thinking when writing proofs.
  - Complete.

What are Axioms？
  - They are statements that describe the very basic behaviour of numbers, sets, or whatever you're working with. They are used as assumptions in proofs.
  - They are so basic that you cannot and don't need to prove, that is, **they are supposed to be obviously TRUE**.
  - Incomplete.

Words
  - edifice [ˈedɪfɪs] n.大厦；宏伟建筑
  - subjectivity n.主观性；主观主义
  - contradiction [ˌkɒntrəˈdɪkʃ(ə)n] n.矛盾；反驳；否定
  - stand on a strong footing 站稳脚跟
  - follow from 由……引起：指某个结果是由某个原因或前提所导致的

## String

Let A be any set.

DEF: the set of n-tuple of elements

$$ A^n = {<a_1, ..., a_n> : a_i \in A} $$

> Order makes sense.

DEF: $$ A^{<\omega} = A^0 \cup A^2 \cup ... $$ the set of strings of elements from A.

E.G. If A is the whole alphabet, then every English word is a member of $$ A^{<\omega} $$.

> `cabaca` can be the short form of <c, a, b, a, c, a>

## Sentential Logic

> Simpler toy example (incomplete) of `first-order logic` (complete). Widely used in circuits & machine learning.

Basic building block is `sentence`, which can be either TRUE or FALSE.

### Language of Sentential Logic

Symbols: 
  - Parenthesis: ( )
  - Operation: $$ \neg \land \lor \Rightarrow \Leftrightarrow \equiv $$
  - Variable symbols: P Q $$ A_1  A_2  A_3 $$ ...

An `experssion` is a string of symbols.

> Only some strings of symbols are valid expressions. Bad expression: $$ \Rightarrow \Leftrightarrow \Rightarrow \Leftrightarrow ABAB $$

DEF: `Well formed formulas, WFF`

WFF are strings of symbols built as follows:
  - Every variable symbol is WFF.
  - If P and Q are WFF, so are:
    - $$ \neg P $$
    - $$ (P \land Q) $$
    - $$ (P \lor Q) $$
    - $$ (P \implies)

### Truth Assignments

Words
  - sentence 命题
  - deduce [dɪˈdjuːs] v.推断；演绎；推论
    - deductive 演绎的 deduction 演绎
    - deduct 减去、扣除 deductible 可扣除的
