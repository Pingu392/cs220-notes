# CS 220 — Discrete Mathematics Exam Notes

> Based on Lectures 1–4. Written for fast review and exam practice.

---

# Lecture 1 — Propositional Logic

## 1. Logic

**Logic** = the study of formal reasoning.

The point of logic is to remove ambiguity. A logical statement should have a well-defined meaning.

---

## 2. Propositions

**Proposition** = a statement that has exactly one truth value: **True** or **False**.

Examples:
- `4 is an odd number.` → proposition, False
- `There are infinitely many prime numbers.` → proposition, True
- `It will rain tomorrow.` → still a proposition even if we do not know its truth value yet

**Non-proposition** = a sentence that cannot be assigned True or False.

Examples:
- `What are you doing?` → question
- `Have a nice day.` → command

### Truth value

The **truth value** tells whether a proposition is True or False.

A proposition is still a proposition even if:
- we do not know whether it is true,
- it refers to the future,
- it is a matter of opinion.

---

## 3. Propositional Variables

Letters such as $p$, $q$, and $r$ represent propositions.

Example:
- $p$: January has 31 days.
- $q$: February has 27 days.

A **compound proposition** combines propositions using logical operations.

---

## 4. Logical Operations

| Operation | Example |
|---|---|
| Conjunction — AND | $p \land q$ is True only when both $p$ and $q$ are True. |
| Disjunction — inclusive OR | $p \lor q$ is True when at least one of $p$ or $q$ is True. It is False only when both are False. |
| Exclusive OR — XOR | $p \oplus q$ is True when exactly one of $p$ and $q$ is True. |
| Negation — NOT | $\neg p$ reverses the truth value of $p$. |
| Conditional | $p \to q$ means “if $p$, then $q$.” It is False only when $p$ is True and $q$ is False. |
| Biconditional | $p \leftrightarrow q$ means “$p$ if and only if $q$.” It is True when $p$ and $q$ have the same truth value. |

### Conjunction: $p \land q$

| $p$ | $q$ | $p \land q$ |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

English words such as **and**, **but**, **although**, and **despite the fact that** can represent conjunction.

### Disjunction: $p \lor q$

| $p$ | $q$ | $p \lor q$ |
|---|---|---|
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |

Normal logical OR is **inclusive**: both propositions are allowed to be true.

### Exclusive OR: $p \oplus q$

| $p$ | $q$ | $p \oplus q$ |
|---|---|---|
| T | T | F |
| T | F | T |
| F | T | T |
| F | F | F |

Think: **one or the other, but not both**.

### Negation: $\neg p$

| $p$ | $\neg p$ |
|---|---|
| T | F |
| F | T |

---

## 5. Order of Operations

From highest priority to lowest:

1. $\neg$
2. $\land$
3. $\lor$
4. $\to$
5. $\leftrightarrow$

Use parentheses whenever possible.

Example:

$$
p \lor \neg q \land r
$$

means

$$
p \lor (\neg q \land r)
$$

not

$$
(p \lor \neg q)\land r.
$$

---

## 6. Truth Tables

A **truth table** lists every possible assignment of truth values.

If there are $n$ propositional variables:

$$
\text{number of rows}=2^n
$$

Examples:
- 2 variables → $2^2=4$ rows
- 3 variables → $2^3=8$ rows
- 4 variables → $2^4=16$ rows

### Exam use

Truth tables can be used to:
- evaluate compound propositions,
- prove a tautology,
- prove a contradiction,
- test logical equivalence,
- test whether an argument is valid.

---

## 7. Conditional Statements

A conditional has the form:

$$
p \to q
$$

- $p$ = **hypothesis**
- $q$ = **conclusion**

Truth table:

| $p$ | $q$ | $p \to q$ |
|---|---|---|
| T | T | T |
| T | F | **F** |
| F | T | T |
| F | F | T |

### The one row to remember

A conditional is False only when:

> the hypothesis happens, but the promised conclusion does not.

Think of $p \to q$ like a contract.

“If you mow the lawn, I will pay you.”

The contract is broken only if:
- you mow the lawn = $p$ is True,
- you are not paid = $q$ is False.

If $p$ is False, the conditional is automatically True.

### Common English forms of $p \to q$

- If $p$, then $q$
- If $p$, $q$
- $q$ if $p$
- $p$ implies $q$
- $q$ whenever $p$

---

## 8. Converse, Contrapositive, and Inverse

Start with:

$$
p \to q
$$

| Name | Example |
|---|---|
| Original | $p \to q$ |
| Converse | $q \to p$ |
| Contrapositive | $\neg q \to \neg p$ |
| Inverse | $\neg p \to \neg q$ |

### Critical fact

The original conditional is logically equivalent to its **contrapositive**:

$$
p \to q \equiv \neg q \to \neg p
$$

The converse and inverse are **not automatically equivalent** to the original.

---

## 9. Biconditional

$$
p \leftrightarrow q
$$

Read:
- “$p$ if and only if $q$”
- “$p$ iff $q$”

True when both sides have the same truth value.

| $p$ | $q$ | $p \leftrightarrow q$ |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | T |

Equivalent form:

$$
p \leftrightarrow q
\equiv
(p \to q)\land(q\to p)
$$

---

## 10. Tautology and Contradiction

**Tautology** = always True.

Example:

$$
p\lor\neg p
$$

**Contradiction** = always False.

Example:

$$
p\land\neg p
$$

### Fast disproof

To show an expression is **not** a tautology:
- find one row where it is False.

To show an expression is **not** a contradiction:
- find one row where it is True.

---

## 11. Logical Equivalence

Two propositions are **logically equivalent** if they have the same truth value under every possible truth assignment.

Notation:

$$
p \equiv q
$$

Equivalent statements can replace each other inside larger expressions.

Example:

$$
\neg\neg p \equiv p
$$

so:

$$
\neg\neg p\land q \equiv p\land q
$$

### Two ways to prove equivalence

1. Build a truth table and show the final columns match.
2. Rewrite one expression into the other using known logical laws.

To disprove equivalence, one mismatching truth-table row is enough.

---

## 12. Laws of Propositional Logic

| Law | Example |
|---|---|
| Idempotent | $p\lor p\equiv p$; $p\land p\equiv p$ |
| Associative | $(p\lor q)\lor r\equiv p\lor(q\lor r)$; $(p\land q)\land r\equiv p\land(q\land r)$ |
| Commutative | $p\lor q\equiv q\lor p$; $p\land q\equiv q\land p$ |
| Distributive | $p\land(q\lor r)\equiv(p\land q)\lor(p\land r)$; $p\lor(q\land r)\equiv(p\lor q)\land(p\lor r)$ |
| Identity | $p\land T\equiv p$; $p\lor F\equiv p$ |
| Domination | $p\lor T\equiv T$; $p\land F\equiv F$ |
| Double Negation | $\neg\neg p\equiv p$ |
| Complement | $p\lor\neg p\equiv T$; $p\land\neg p\equiv F$ |
| De Morgan | $\neg(p\lor q)\equiv\neg p\land\neg q$; $\neg(p\land q)\equiv\neg p\lor\neg q$ |
| Absorption | $p\lor(p\land q)\equiv p$; $p\land(p\lor q)\equiv p$ |
| Conditional Identity | $p\to q\equiv\neg p\lor q$ |
| Biconditional Identity | $p\leftrightarrow q\equiv(p\to q)\land(q\to p)$ |

### De Morgan's Law — easiest memory rule

When a negation moves through parentheses:

1. negate each part,
2. flip AND ↔ OR.

$$
\neg(p\land q)\equiv\neg p\lor\neg q
$$

$$
\neg(p\lor q)\equiv\neg p\land\neg q
$$

### Example of rewriting

Prove:

$$
p\to q\equiv\neg q\to\neg p
$$

Start:

$$
p\to q
$$

Conditional identity:

$$
\neg p\lor q
$$

Commutative:

$$
q\lor\neg p
$$

Double negation:

$$
\neg\neg q\lor\neg p
$$

Conditional identity in reverse:

$$
\neg q\to\neg p
$$

---

# Lecture 2 — Predicate Logic

## 1. Predicate

A **predicate** is a logical statement containing one or more unresolved variables.

Example:

$$
P(x): x\text{ is odd}
$$

This is not yet a proposition because the truth value depends on $x$.

- $P(3)$ → True
- $P(4)$ → False

Once every variable is assigned a value, the predicate becomes a proposition.

A predicate can contain multiple variables.

Example:

$$
Q(x,y): x<y
$$

Both $x$ and $y$ must be resolved before the statement has one truth value.

---

## 2. Domain

The **domain** is the set of allowed values for a variable.

Example:

$$
P(x): x\text{ is odd}
$$

Possible domain: all integers.

The domain matters because it changes what values you are allowed to use.

If the domain is not obvious, state it.

---

## 3. Quantifiers

### Universal quantifier

$$
\forall x\,P(x)
$$

means:

> For every $x$ in the domain, $P(x)$ is true.

For a finite domain $\{x_1,\ldots,x_n\}$:

$$
\forall x\,P(x)
\equiv
P(x_1)\land P(x_2)\land\cdots\land P(x_n)
$$

### Existential quantifier

$$
\exists x\,P(x)
$$

means:

> There is at least one $x$ in the domain for which $P(x)$ is true.

For a finite domain:

$$
\exists x\,P(x)
\equiv
P(x_1)\lor P(x_2)\lor\cdots\lor P(x_n)
$$

---

## 4. How to Prove or Disprove Quantified Statements

| Statement | Example |
|---|---|
| Show $\forall x\,P(x)$ is True | Choose an **arbitrary** $x$ and prove $P(x)$. |
| Show $\forall x\,P(x)$ is False | Give one **counterexample** where $P(x)$ is False. |
| Show $\exists x\,P(x)$ is True | Give one specific example where $P(x)$ is True. |
| Show $\exists x\,P(x)$ is False | Show $P(x)$ fails for every element of the domain. |

### Universal statement

To prove:

$$
\forall x\,P(x)
$$

you cannot simply test a few examples.

You must prove the statement for an **arbitrary** element.

### Counterexample

One counterexample destroys a universal claim.

Claim:

$$
\forall x\in\mathbb{Z}^+,\quad x^2>x
$$

Choose $x=1$:

$$
1^2=1
$$

but $1\not>1$.

Therefore the universal statement is False.

### Existential statement

To prove:

$$
\exists x\,P(x)
$$

one working example is enough.

Example:

$$
\exists x\,(x\text{ is even}\land x\text{ is prime})
$$

Choose $x=2$.

### Empty-domain edge cases from the slides

- $\forall x\,P(x)$ is automatically True when the domain is empty.
- $\exists x\,P(x)$ is automatically False when the domain is empty.

---

## 5. Compound Quantified Statements

Quantifiers can be combined with:

$$
\neg,\land,\lor,\to,\leftrightarrow
$$

Example:

$$
\exists x(P(x)\land\neg Q(x))
$$

means:

> There exists an $x$ for which $P(x)$ is true and $Q(x)$ is false.

---

## 6. Quantifier Scope and Precedence

The lecture states that quantifiers apply before the logical operations that follow unless parentheses extend their scope.

Example:

$$
\forall x\,P(x)\land Q(x)
$$

is read as:

$$
(\forall x\,P(x))\land Q(x)
$$

not:

$$
\forall x(P(x)\land Q(x))
$$

### Exam habit

Always write parentheses around the part controlled by a quantifier.

---

## 7. Free and Bound Variables

**Bound variable** = controlled by a quantifier.

**Free variable** = not controlled by a quantifier.

Example:

$$
\forall x(P(x)\to Q(y))
$$

- $x$ is bound.
- $y$ is free.

Therefore the whole expression is **not** a proposition.

A logical expression is a proposition only when **every variable is bound or otherwise assigned**.

Example:

$$
\forall x(P(x)\to Q(x))
$$

has no free variables, so it is a proposition.

---

## 8. Translating English into Quantifiers

| English pattern | Example |
|---|---|
| Every $X$ that is $P$ is also $Q$ | $\forall x(P(x)\to Q(x))$ |
| All $X$ are $P$ | $\forall x\,P(x)$ |
| Some $X$ is $P$ | $\exists x\,P(x)$ |
| Some $X$ is both $P$ and $Q$ | $\exists x(P(x)\land Q(x))$ |
| No $X$ is $P$ | $\forall x\,\neg P(x)$ or $\neg\exists x\,P(x)$ |
| At least one $X$ is not $P$ | $\exists x\,\neg P(x)$ |

### Important distinction

These are **not** equivalent:

$$
\exists x(S(x)\land C(x))
$$

and

$$
(\exists x\,S(x))\land(\exists x\,C(x))
$$

The first says **the same person** satisfies both predicates.

The second allows two different people.

---

## 9. Negating Quantifiers

| Law | Example |
|---|---|
| Negated universal | $\neg\forall x\,P(x)\equiv\exists x\,\neg P(x)$ |
| Negated existential | $\neg\exists x\,P(x)\equiv\forall x\,\neg P(x)$ |

### English meaning

$$
\neg\forall x\,P(x)
$$

means:

> Not everyone is $P$.

Equivalent:

$$
\exists x\,\neg P(x)
$$

> Someone is not $P$.

Likewise:

$$
\neg\exists x\,P(x)
$$

means:

> No one is $P$.

Equivalent:

$$
\forall x\,\neg P(x)
$$

> Everyone is not $P$.

### Mechanical rule

Every time a negation passes through a quantifier:

$$
\forall \leftrightarrow \exists
$$

and the negation continues inward.

---

## 10. Negating Compound Quantified Statements

Example:

$$
\neg\exists x(P(x)\to Q(x))
$$

Flip the quantifier:

$$
\forall x\,\neg(P(x)\to Q(x))
$$

Use the conditional identity:

$$
\forall x\,\neg(\neg P(x)\lor Q(x))
$$

Use De Morgan:

$$
\forall x(\neg\neg P(x)\land\neg Q(x))
$$

Double negation:

$$
\forall x(P(x)\land\neg Q(x))
$$

---

## 11. Nested Quantifiers

A predicate with multiple variables may require multiple quantifiers.

Example:

$$
\forall x\exists y\,P(x,y)
$$

Both variables are bound.

### Same-type quantifiers

$$
\forall x\forall y\,S(x,y)
$$

means:

> Every $x$ satisfies $S$ with every $y$.

$$
\exists x\exists y\,S(x,y)
$$

means:

> At least one pair $(x,y)$ satisfies $S$.

### Mixed quantifiers

Order matters.

$$
\exists x\forall y\,S(x,y)
$$

means:

> There is one particular $x$ that works for every $y$.

But:

$$
\forall x\exists y\,S(x,y)
$$

means:

> For every $x$, there is some $y$ that works.

The $y$ may be different for each $x$.

### Fast way to think about mixed quantifiers

Read left to right.

- $\forall$ chooses a value that may make your job difficult.
- $\exists$ gets to choose a value that makes the statement work.

Example:

$$
\forall x\exists y(x+y=0)
$$

over the integers is True because after $x$ is chosen, choose:

$$
y=-x.
$$

But:

$$
\exists y\forall x(x+y=0)
$$

is False because one fixed $y$ cannot cancel every possible $x$.

---

## 12. Negating Nested Quantifiers

Negate one quantifier at a time.

Example:

$$
\neg\exists x\forall y\,L(x,y)
$$

becomes:

$$
\forall x\exists y\,\neg L(x,y)
$$

General pattern:

$$
\neg\forall x\forall y\,P(x,y)
\equiv
\exists x\exists y\,\neg P(x,y)
$$

Then continue pushing the negation through the predicate using ordinary propositional laws.

> **Slide note:** Lecture 2 slide 38 displays an extra duplicated $\forall y$ in one worked line. The rule stated on the slide itself is the part to rely on: each quantifier crossed by the negation flips $\forall\leftrightarrow\exists$.

---

## 13. Excluding the Same Object

Suppose:

$$
S(x,y): x\text{ sent an email to }y
$$

Then:

$$
\forall x\forall y\,S(x,y)
$$

includes the case $x=y$.

To mean “everyone emailed everyone else,” use:

$$
\forall x\forall y((x\ne y)\to S(x,y))
$$

The conditional acts as a filter:
- if $x=y$, the hypothesis $x\ne y$ is False, so that case does not force an email;
- if $x\ne y$, then $S(x,y)$ must hold.

---

## 14. Expressing Uniqueness

Existential quantification alone means “at least one.”

$$
\exists x\,L(x)
$$

does **not** mean exactly one.

To say exactly one person was late:

$$
\exists x\left(L(x)\land\forall y(y\ne x\to\neg L(y))\right)
$$

Meaning:
1. $x$ was late.
2. Every other $y$ was not late.

---

## 15. Null Qualification Rule

| Rule | Example |
|---|---|
| Move a quantifier across a conjunction when the other expression does not contain that quantified variable | $\forall y(P(y)\land Q)\equiv(\forall yP(y))\land Q$, provided $Q$ does not contain $y$. |

The lecture says the same idea also works with $\exists$ in place of $\forall$.

Example:

$$
\exists x(L(x)\land\forall y(y\ne x\to\neg L(y)))
$$

can be rewritten as:

$$
\exists x\forall y(L(x)\land(y\ne x\to\neg L(y)))
$$

because $L(x)$ does not contain $y$.

The lecture explicitly warns that replacing the conjunction with a biconditional does **not** preserve this equivalence.

---

# Lecture 3 — Logical Reasoning and Rules of Inference

## 1. Logical Arguments

A logical argument contains:
- **hypotheses**: $p_1,p_2,\ldots,p_n$
- a **conclusion**: $q$

Notation:

$$
p_1,p_2,\ldots,p_n\therefore q
$$

$\therefore$ means **therefore**.

### Valid argument

An argument is valid when:

> whenever every hypothesis is True, the conclusion is also True.

### Invalid argument

An argument is invalid if there is at least one truth assignment where:
- every hypothesis is True,
- the conclusion is False.

That single row is enough to disprove validity.

---

## 2. Testing Validity with a Truth Table

For an argument:

$$
p_1,p_2,\ldots,p_n\therefore q
$$

look only at rows where **all hypotheses are True**.

- If $q$ is True in every such row → valid.
- If $q$ is False in even one such row → invalid.

Equivalent test:

$$
(p_1\land p_2\land\cdots\land p_n)\to q
$$

must be a tautology.

### Contradictory hypotheses

If the hypotheses can never all be True at the same time, there is no row that can violate validity.

Example:

$$
p,\neg p\therefore q
$$

is valid under the definition used in the lecture.

---

## 3. Argument Form Matters

Validity depends on **structure**, not whether the English sentences happen to be true in real life.

Example:

$$
p\to q,\ q\therefore p
$$

is invalid even if $p$ and $q$ happen to both be True in some real example.

---

## 4. Common Invalid Forms

| Invalid form | Example |
|---|---|
| Converse error | $p\to q,\ q\therefore p$ |
| Inverse error | $p\to q,\ \neg p\therefore\neg q$ |

Do not confuse either one with:
- Modus Ponens
- Modus Tollens

---

## 5. Rules of Inference

Rules of inference are pre-proven valid argument patterns.

| Rule | Example |
|---|---|
| Modus Ponens | $p\to q,\ p\therefore q$ |
| Modus Tollens | $p\to q,\ \neg q\therefore\neg p$ |
| Addition | $p\therefore p\lor q$ |
| Simplification | $p\land q\therefore p$ |
| Conjunction | $p,\ q\therefore p\land q$ |
| Hypothetical Syllogism | $p\to q,\ q\to r\therefore p\to r$ |
| Disjunctive Syllogism | $p\lor q,\ \neg p\therefore q$ |
| Resolution | $p\lor q,\ \neg p\lor r\therefore q\lor r$ |

### What these rules do

They let you move from known statements to new statements without rebuilding a truth table every time.

---

## 6. Logical Proof Format

A logical proof is a sequence of justified steps.

Each line contains:
1. a statement,
2. a justification.

Example format:

| Step | Statement | Justification |
|---|---|---|
| 1 | $r$ | Hypothesis |
| 2 | $p\lor r$ | Addition, 1 |
| 3 | $(p\lor r)\to q$ | Hypothesis |
| 4 | $q$ | Modus Ponens, 2, 3 |

The final line must be the conclusion you were asked to prove.

### Direction matters

Logical laws such as equivalences can be used in either direction.

Rules of inference do **not** allow you to reverse an argument.

You work:

$$
\text{hypotheses}\longrightarrow\text{conclusion}
$$

not backward from the conclusion and pretend it proves the hypotheses.

---

## 7. Rules of Inference with Quantifiers

Before applying ordinary propositional inference rules, a quantified expression often needs to be instantiated.

### Arbitrary vs. particular

**Arbitrary element**
- has no special property beyond being in the domain,
- can represent any domain member.

**Particular element**
- is one specific object,
- may have special properties.

---

## 8. Quantifier Inference Rules

| Rule | Example |
|---|---|
| Universal Instantiation | From $\forall xP(x)$ and an element $c$, conclude $P(c)$. |
| Universal Generalization | If $c$ is arbitrary and $P(c)$ has been proved, conclude $\forall xP(x)$. |
| Existential Instantiation | From $\exists xP(x)$, introduce a new particular element $c$ with $P(c)$. |
| Existential Generalization | From $P(c)$ for some element $c$, conclude $\exists xP(x)$. |

The lecture applies these rules to non-nested quantifiers.

### Universal Instantiation

$$
\forall xP(x)
$$

lets you substitute any element $c$:

$$
P(c)
$$

### Universal Generalization

To conclude:

$$
\forall xP(x)
$$

the element $c$ used in the proof must be **arbitrary**.

### Existential Instantiation

From:

$$
\exists xP(x)
$$

you may introduce a new name, say $c$, representing one particular element satisfying $P$.

### Important restriction

Every use of Existential Instantiation must introduce a **new element name**.

Do not use the same name for two independent existential claims.

Example:

$$
\exists xC(x)
$$

and

$$
\exists xD(x)
$$

do not allow you to assume one person satisfies both $C$ and $D$.

---

# Lecture 4 — Introduction to Proofs

## 1. Mathematical Definitions You Need

These definitions are tools. Proofs often begin by expanding a word into its formal definition.

---

## 2. Even and Odd Integers

**Even integer**:

$$
n=2k
$$

for some integer $k$.

**Odd integer**:

$$
n=2k+1
$$

for some integer $k$.

**Parity** = whether an integer is even or odd.

- same parity → both even or both odd
- opposite parity → one even and one odd

Examples:

$$
17=2(8)+1
$$

so 17 is odd.

$$
-6=2(-3)
$$

so $-6$ is even.

---

## 3. Rational Numbers

A real number $r$ is **rational** if:

$$
r=\frac ab
$$

for integers $a,b$ with:

$$
b\ne0.
$$

The representation does not have to be unique.

Example:

$$
\frac12=\frac24.
$$

Every integer is rational because:

$$
n=\frac n1.
$$

---

## 4. Divisibility

$$
a\mid b
$$

means:

> $a$ divides $b$.

Definition from the lecture:

$$
b=ac
$$

for some integer $c$, with $a\ne0$.

If $a\mid b$:
- $a$ is a factor/divisor of $b$,
- $b$ is a multiple of $a$.

Example:

$$
3\mid12
$$

because:

$$
12=3(4).
$$

But:

$$
5\nmid12
$$

because no integer $c$ satisfies:

$$
12=5c.
$$

---

## 5. Prime and Composite

**Prime**: an integer $n>1$ whose only positive divisors are $1$ and $n$.

**Composite**: an integer $n>1$ for which there exists an integer $d$ such that:

$$
1<d<n
$$

and:

$$
d\mid n.
$$

Every integer greater than 1 is either prime or composite, not both.

---

## 6. Negating Inequalities

| Statement | Example |
|---|---|
| Negation of $a<b$ | $a\ge b$ |
| Negation of $a>b$ | $a\le b$ |
| Positive | $a>0$ |
| Negative | $a<0$ |
| Non-negative | $a\ge0$ |
| Non-positive | $a\le0$ |

This becomes especially important in proof by contradiction and contrapositive reasoning.

---

## 7. What Is a Mathematical Proof?

**Theorem** = a statement that can be proved true.

**Proof** = a sequence of logical steps that begins from:
- assumptions,
- definitions,
- axioms,
- previously established facts,

and ends at the theorem's conclusion.

Standard style:
- begin with `Proof:`
- finish with $\square$

A proof should convince a skeptical reader that every step is justified.

---

## 8. Universal and Existential Theorems

A **universal statement** claims something for every element.

A **existential statement** claims at least one element exists.

Many theorems are universal even when the words “for all” are not written explicitly.

---

## 9. Proof by Exhaustion

Use when the domain is small and finite.

Method:
1. list every possible case,
2. prove the claim in every case.

Example domain:

$$
n\in\{1,2,3\}
$$

Then check $n=1$, $n=2$, and $n=3$ separately.

### Limitation

This becomes useless when the domain is large or infinite.

---

## 10. Universal Generalization

To prove a universal statement:

1. choose one **arbitrary** object,
2. assume only what the theorem gives you,
3. prove the conclusion for that object.

Because the object was arbitrary, the result applies to every object in the domain.

---

## 11. Counterexample

A **counterexample** is one assignment that makes a universal claim False.

To disprove:

$$
\forall x\,P(x)
$$

find one $x$ where:

$$
P(x)
$$

is False.

For a conditional:

$$
H\to C
$$

a counterexample must make:
- $H$ True,
- $C$ False.

That is the only way a conditional fails.

---

## 12. Proving Existential Statements

### Constructive proof

Give a specific example.

Example claim:

> There is an integer that can be written as the sum of two squares in two different ways.

The lecture uses:

$$
50=1^2+7^2=5^2+5^2.
$$

This directly proves existence.

### Nonconstructive proof

Prove something exists without explicitly naming it.

The lecture notes that this is often done using contradiction.

---

## 13. Disproving Existential Statements

To disprove:

$$
\exists xP(x)
$$

prove:

$$
\forall x\neg P(x).
$$

This is De Morgan's law for quantifiers.

Example claim:

> There is a real number whose square is negative.

Disprove it by proving every real square is non-negative.

---

## 14. How Detailed Should a Proof Be?

The lecture expects:
- every important step to be justified,
- roughly one algebraic rule per step when detail matters,
- enough explanation that a reader can follow the logic.

Do not jump across unexplained steps.

---

## 15. Facts the Lecture Allows You to Use

The slides list facts such as:

- ordinary rules of algebra,
- integers are closed under addition, subtraction, and multiplication,
- every integer is either even or odd,
- there is no integer strictly between $n$ and $n+1$,
- real numbers have an order,
- squares of real numbers are non-negative,
- every real number is positive, negative, or zero.

Inequality facts:
- adding the same value to both sides preserves the inequality,
- multiplying by a positive value preserves the direction,
- multiplying by a negative value reverses the direction.

---

## 16. Proof Writing Vocabulary

| Term | Example |
|---|---|
| Let | Introduces a variable: “Let $n$ be a positive integer.” |
| Suppose | Introduces a variable or assumption. |
| Since | Reminds the reader of an established fact before using it. |
| Thus / Therefore / It follows that | Signals a conclusion from earlier steps. |
| By definition | Uses the formal definition of a concept. |
| By assumption | Uses something already assumed. |
| In other words | Restates a claim more concretely. |
| Gives / yields | Connects one algebraic line to the next. |

---

## 17. Proof Writing Best Practices

- Clearly mark where the proof begins and ends.
- Write in complete sentences.
- Introduce every variable before using it.
- State assumptions up front.
- Explain why important algebraic or logical steps are valid.
- Do not use the theorem you are proving as part of its own proof.

---

## 18. Existential Instantiation Inside Mathematical Proofs

Many definitions contain the phrase:

> “for some integer $k$”

That means an object is known to exist, so you can give it a name.

Example:

If $n$ is odd, then by definition:

$$
n=2k+1
$$

for some integer $k$.

### Critical mistake to avoid

If two different existence statements introduce values, do not automatically use the same variable name.

For example, if:

$$
a\mid b
$$

and:

$$
a\mid c,
$$

write:

$$
b=ak
$$

and:

$$
c=a\ell
$$

for possibly different integers $k$ and $\ell$.

Using the same $k$ would incorrectly assume the same multiplier.

---

## 19. Common Proof Mistakes

### Generalizing from examples

Testing a few values does not prove a universal theorem.

### Skipping steps

A missing algebraic or logical justification creates a gap.

### Circular reasoning

Do not use the conclusion you are trying to prove as one of your assumptions.

### Assuming unproven facts

Every claim used should come from:
- a definition,
- a hypothesis,
- an allowed algebraic fact,
- a previously proved theorem.

---

# Direct Proof

## 20. Form of Direct Proof

Most theorems can be viewed as:

$$
H\to C
$$

A **direct proof** does this:

1. Assume $H$.
2. Use definitions/algebra/known facts.
3. Derive $C$.

### Standard opening

> Let $n$ be an integer satisfying the hypothesis. We will show the conclusion.

---

## 21. Direct Proof Example — Odd Square

Theorem:

> The square of every odd integer is odd.

Let $n$ be odd.

By definition:

$$
n=2k+1
$$

for some integer $k$.

Square:

$$
n^2=(2k+1)^2
$$

Expand:

$$
n^2=4k^2+4k+1
$$

Factor:

$$
n^2=2(2k^2+2k)+1.
$$

Since $k$ is an integer:

$$
2k^2+2k
$$

is an integer.

Therefore $n^2$ has the form:

$$
2(\text{integer})+1,
$$

so $n^2$ is odd. $\square$

### Pattern to recognize

If the goal is “prove something is odd,” try to rewrite it as:

$$
2k+1.
$$

If the goal is “prove something is even,” try to rewrite it as:

$$
2k.
$$

If the goal is “prove something is rational,” try to rewrite it as:

$$
\frac{\text{integer}}{\text{nonzero integer}}.
$$

---

## 22. Direct Proof Example — Sum of Rationals

Suppose $r$ and $s$ are rational.

Then:

$$
r=\frac ab,\qquad s=\frac cd
$$

for integers $a,b,c,d$ with:

$$
b\ne0,\qquad d\ne0.
$$

Then:

$$
r+s
=
\frac ab+\frac cd
=
\frac{ad+bc}{bd}.
$$

- $ad+bc$ is an integer.
- $bd$ is an integer.
- $bd\ne0$.

Therefore $r+s$ is rational.

---

# Proof by Contrapositive

## 23. What It Is

Original theorem:

$$
H\to C
$$

Contrapositive:

$$
\neg C\to\neg H
$$

These are logically equivalent.

So instead of proving the original directly, you may prove its contrapositive.

### Method

1. Assume $\neg C$.
2. Prove $\neg H$.
3. Conclude the original conditional is true.

---

## 24. When Contrapositive Is Useful

Use it when the negation of the conclusion gives you a much more concrete expression than the original hypothesis.

Example theorem:

> If $n^2$ is even, then $n$ is even.

Direct approach:
- assume $n^2$ is even,
- trying to extract information about $n$ is awkward.

Contrapositive:
- assume $n$ is **not even**,
- since every integer is even or odd, $n$ is odd,
- write $n=2k+1$,
- prove $n^2$ is odd.

Much easier.

---

## 25. Contrapositive Example — Even Square

Theorem:

$$
n^2\text{ even}\to n\text{ even}
$$

Contrapositive:

$$
n\text{ odd}\to n^2\text{ odd}
$$

Assume:

$$
n=2k+1.
$$

Then:

$$
n^2=(2k+1)^2
=4k^2+4k+1
=2(2k^2+2k)+1.
$$

Therefore $n^2$ is odd.

So the contrapositive is true, which proves the original theorem.

---

## 26. Direct vs. Contrapositive

Choose whichever side gives you a usable mathematical definition.

Example:

> If $x$ is irrational, then $\sqrt{x}$ is irrational.

Direct:
- “$x$ is irrational” gives no simple algebraic form.

Contrapositive:
- assume $\sqrt{x}$ is rational,
- write:

$$
\sqrt{x}=\frac ab,
$$

- square both sides:

$$
x=\frac{a^2}{b^2},
$$

which gives a concrete rational form.

---

## 27. Contrapositive with Multiple Hypotheses

Suppose the theorem has form:

$$
(P\land Q)\to C.
$$

The raw contrapositive is:

$$
\neg C\to\neg(P\land Q).
$$

Using De Morgan:

$$
\neg C\to(\neg P\lor\neg Q).
$$

The lecture gives two useful equivalent strategies:

### Form A

Assume:
- $P$ is True,
- $C$ is False.

Prove:

$$
\neg Q.
$$

Symbolically:

$$
(P\land\neg C)\to\neg Q.
$$

### Form B

Assume:
- $Q$ is True,
- $C$ is False.

Prove:

$$
\neg P.
$$

This avoids trying to prove a disjunction directly.

### Lecture example

Theorem:

> If $x$ is rational and $y$ is irrational, then $x+y$ is irrational.

One contrapositive strategy:

Assume:
- $x$ is rational,
- $x+y$ is rational.

Show:
- $y$ is rational.

Because:

$$
y=(x+y)-x.
$$

That negates the original second hypothesis, completing the contrapositive strategy.

---

# Exam Survival Summary

## You should be able to do these without looking them up

1. Build a truth table with $2^n$ rows.
2. Remember that $p\to q$ is False only for $T\to F$.
3. Write converse, inverse, and contrapositive correctly.
4. Apply De Morgan's laws.
5. Rewrite $p\to q$ as $\neg p\lor q$.
6. Recognize tautologies and contradictions.
7. Use the propositional laws to rewrite equivalent statements.
8. Translate English into $\forall$, $\exists$, $\land$, $\lor$, $\neg$, and $\to$.
9. Negate quantified statements by flipping each quantifier and pushing $\neg$ inward.
10. Distinguish free variables from bound variables.
11. Know that nested quantifier order matters.
12. Test argument validity by looking for a row with all hypotheses True and conclusion False.
13. Recognize Modus Ponens, Modus Tollens, syllogisms, Addition, Simplification, Conjunction, and Resolution.
14. Use Universal/Existential Instantiation and Generalization correctly.
15. Expand definitions immediately in proofs:
    - even → $2k$
    - odd → $2k+1$
    - rational → $a/b$
    - divides → $b=ac$
16. Disprove a universal theorem with one counterexample.
17. Prove an existential theorem with one witness.
18. Write a direct proof from hypothesis to conclusion.
19. Recognize when the contrapositive gives an easier starting point.
20. Never reuse one existentially introduced variable as though two separate existence statements referred to the same object.

---

# Fast Proof Strategy

When a proof question appears, ask in this order:

**1. What exactly is the hypothesis?**  
Write it down.

**2. What exactly is the conclusion?**  
Write it down.

**3. Are there definition words?**  
Immediately expand:
- odd,
- even,
- rational,
- divides,
- prime,
- composite.

**4. Is it universal?**  
Use an arbitrary element.

**5. Is it existential?**  
Look for one witness.

**6. Are you trying to disprove a universal claim?**  
Look for one counterexample.

**7. Is direct proof awkward?**  
Write the contrapositive and see whether its assumptions give cleaner algebra.

**8. Justify every meaningful step.**  
Do not make logical jumps.
