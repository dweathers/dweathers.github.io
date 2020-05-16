# MATH 174

## 0. What is discrete mathematics?

### 0.1 It's math you do quietly, right?

The phrase "discrete mathematics" is often used nebulously to refer to a certain branch of mathematics that, from the college point of view, is "not calculus" or perhaps is applicable to computer science. In this section, we will try to understand what it means for a topic to fall under the umbrella of discrete mathematics.

### 0.2 A tale of two sets

Throughout high school and college mathematics so far, you have largely been working with $\mathbf{R}$, the set of real numbers. This set includes virtually every number you can imagine, including $0$, $-1$, $3/4$, $0.6$, $\sqrt{2}$, and $\pi$. (If you know what a complex number is, $\mathbf{R}$ does not include those.) 

One of the distinguishing features of $\mathbf{R}$ is their density. Here's the idea. If I give you any two real numbers -- say, $0$ and $1$ -- you can find one in between -- say, $1/\pi$. Then between $0$ and $1/\pi$ you can find another. And so on.

Another set with which you are familiar is $\mathbf{N}$, the set of natural numbers. The natural numbers are the counting numbers starting with $0$ (in this book, anyway). If I give you two natural numbers like $0$ and $1$, you cannot find another natural in between. In this sense, the natural numbers are -- you guessed it! -- *discrete*. We often call $\mathbf{N}$ **countable** and $\mathbf{R}$ **uncountable**, because the elements of the latter cannot be listed. (You will never get to 1.)

So, **discrete mathematics** is the study of objects that are countable. 

### 0.3 Some examples

Here are some questions we might try to answer using discrete mathematics. In fact, you will be able to answer all these questions by the end of the book.

*Suppose we have a program that will activate condition 4 if conditions 1 and 2 are met but not condition 3. How do we know when condition 4 is active?*

We can use logic to represent this program with the statement $(p \wedge q \wedge \neg r) \to s$, and then use truth tables to determine exactly when condition 4 will trigger.

*Which of these two programs is more efficient?*

A sequence is a function of natural numbers. An example is the number $(a_n)$ of steps it takes to run a computer program with $n$ inputs. If $(a_n)$ grows must faster than $(b_n)$ does, that can tell us that one program scales worse for large quantities of data.

*Some members of a community are sick. How do we know who is at risk of being infected?*

Relations encode relationships between sets of objects. We may compose relations to iterate those relationships over and over again. If person $x$ is sick and has come into contact with person $y$, and $y$ has come into contact with person $z$, and $z$ has since seen $w$, then $w$ is at risk.

### 0.4 The point of this book

-- is to teach you discrete mathematics, of course.

But much more broadly, this book is intended to teach you to *think mathematically*. You may be a student who has never seen any math beyond calculus or algebra, or perhaps you dread doing math. The point of this book is to get you to learn to think deeply, communicate carefully, and not shy away from difficult material. 

As you proceed, have something to write with on hand. Work each example along with the book. Then, at the end of each chapter, work the exercises. Some (denoted with a $*$) are more difficult than others, but are well worth doing to improve your understanding. Work along with someone at roughly your skill level, share solutions and ask each other questions.

Everyone can be a "math person!" So, let's get started.

## 1. Sets

### 1.1 Membership 

For nearly all interested parties, sets form the foundation of all mathematics. Every mathematical objects you have ever encountered can be described as a set, from numbers themselves to functions and matrices. 

We will say that a **set** is an unordered collection of objects, called its **elements**. When $x$ is an element of the set $X$, we write $x \in X$.

*Examples.* Our starting point will be the set of all **natural numbers**,

$$ \mathbf{N} = \{0,1,2,3,\ldots \}.$$

Certain sets are special enough to get their own names, with bold or "blackboard bold" face. Sometimes (especially in ink) you will see $\mathbb{N}$ instead. Note that the elements of the set are enclosed in curly braces. Proper notation is not optional; using the wrong notation is like saying "milk went store" to mean "I went to the store to get milk." Finally, not everyone agrees that $0$ is a natural number, but computer scientists do.

If we take $\mathbf{N}$ and include its negatives, we get the **integers**

$$ \mathbf{Z} = \{\ldots, -2, -1, 0, 1, 2, \ldots \}.$$

Notice that in the case of an infinite set, or even a large finite set, we can use ellipses when a pattern is established. One infinite set that defies a pattern is the set of **prime numbers**. You may recall that a prime number is a positive integer $p$ with exactly two factors: itself and $1$. We may list a few: $2, 3, 5, 7, 11, 13, 17, 19, 23,$ but there is no pattern that allows us to employ ellipses.

Fortunately there is another way to write down a set. All previous examples have used **roster** notation, where the elements are simply listed. It may be more convenient to use **set-builder** notation, where the set is instead described with a rule that exactly characterizes this element. In that case, the set of primes can be written as

$$ \{ \, p \, | \; p \text{ is a prime number} \}.$$

To provide one last example, consider the set of all U.S. states. In roster notation this set is a nightmare: {AL, AK, AZ, AR, CA, CO, CT, DE, FL, GA, HI, ID, IL, IN, IA, KS, KY, LA, ME, MD, MA, MI, MN, MS, MO, MT, NE, NV, NH, NJ, NM, NY, NC, ND, OH, OK, OR, PA, RI, SC, SD, TN, TX, UT, VT, VA, WA, WV, WI, WY}. But in set-builder notation we simply write

$$ \{ \, S \, | \, S \text{ is a U.S. state} \}.$$

**Definition 1.1.1.** Two sets $X$ and $Y$ are **equal** if they contain exactly the same elements, in which case we write $X=Y$.

Remember that sets are unordered, so even $\{a,b\}=\{b,a\}$.

**Definition 1.1.2.** Let $X$ be a finite set. Its **cardinality**, denoted $|X|$, is the number of elements in $X$.

*Example.* If $X=\{a,b,c\}$, then $|X|=3$.

We can talk about the cardinality of infinite sets, but that is far beyond the scope of this course.

### 1.2 Containment

One of the most important ideas when dealing with sets is that of a subset.

**Definition 1.2.1.** Let $X$ and $Y$ be sets. We say $X$ is a **subset** of $Y$ if every element of $X$ is also an element of $Y$.

*Examples.* Put $X = \{a,b,c\}$, $Y = \{a,c\}$, and $Z=\{b\}$. Then $Y \subseteq X$, $Z \subseteq X$, but $Y \not\subseteq Z$ and $Z \not\subseteq Y$.

In mathematics, true statements are either definitions (those taken for granted) or theorems (those proven from the definitions). We will learn to prove more difficult theorems later, but for now we can prove a simple one.

**Theorem 1.2.2.** Every set is a subset of itself.

A proof is simply an argument that convinces its reader of the truth of a mathematical fact. Valid proofs must only use definitions and the hypotheses of the theorem; it is not correct to assume more than you are given. So the ingredients in the proof of this theorem are simply going to be a set and the definition of the word "subset."

*Proof.* Let $X$ be a set. Suppose $x$ is an arbitrary element of $X$. Then, $x$ is also an element of $X$. Because $X$ was shown to have any arbitrary element of $X$, then $X \subseteq X$. $\square$

Notice that the actual make-up of the set $X$ is irrelevant. If $X$ has an element, then $X$ also has that element, and that is all it takes to conclude $X \subseteq X$. It would be incorrect to try to prove $X \subseteq X$ from an example: just because $\{0\}$ is a subset of itself doesn't necessarily mean that $\{0,1\}$ is!

We will discuss logic and proof-writing at length as we continue. For now, let's continue learning about sets and proving the "simple" theorems as we go.

**Definition 1.2.3.** The set with no elements is called the **empty set**, denoted $\{ \}$ or $\varnothing$.

With a little logical sleight-of-hand, we can prove another (much more surprising) theorem.

**Theorem 1.2.4.** The empty set is a subset of every set.

*Proof.* Let $X$ be a set. We may conclude $\varnothing \subseteq X$ if every element of $\varnothing$ is an element of $X$. Observe that this statement is equivalent to saying that *no* elements of $\varnothing$ are *not* elements of $X$. Because there are no elements of $\varnothing$ at all, this statement is true; and we are done. $\square$

Perhaps you already agree with the central claim of the proof, that there are no difference between the statements "everything in $\varnothing$ is in $X$" and "nothing in $\varnothing$ is not in $X$". If you do not, take it on faith for now. When we study predicate logic later you will have the tools to convince yourself of the claim.

Such a statement that relies on the emptiness of $\varnothing$ is said to be **vacuously true**.

When $X \subseteq Y$, we say $Y$ contains $X$ or that $Y$ is a superset of $X$. With the idea of containment in hand we can construct a new type of set.

**Definition 1.2.5.** Let $X$ be a set. Its **power set** is the set $\mathcal{P}(X)$ whose elements are the subsets of $X$. That is,
$$ \mathcal{P}(X) = \{ \, E \, | \, E \subseteq X \, \}.$$

Wait - our *elements* are *sets*? Yes, and this is perfectly fine! Elements can be all sorts of things, other sets included. When we have a "set of sets" we typically refer to it as a family or a collection to avoid using the same word and over and over.

*Example.* Let $X = \{a,b,c\}$. Then

$$ \mathcal{P}(X) = \{ \varnothing, \{a\}, \{b\}, \{c\}, \{a,b\}, \{a,c\}, \{b,c\}, X\}. $$

Notice that the number of sets in $\mathcal{P}(X)$ can be derived from the number of elements in $X$. 

**Theorem 1.2.6.** If $X$ is finite, then $|\mathcal{P}(X)|=2^{|X|}$.

We will come back to prove this theorem much later, once we have learned how to count!

### 1.3 The algebra of sets

You are used to word "algebra" as it refers to a class where you must solve some equations for $x$. If you think about those classes, they are really about *understanding operations and functions of real numbers.* Think about it: a successful algebra student will know how to manipulate sums, products, polynomials, roots, and exponential functions -- ways of combining and mapping real numbers.

So, "algebra" in general refers to the ways objects may be combined and mapped. In this section, we will see many ways that sets can be combined to produce new sets. 

**Definition 1.3.1.** Let $X$ and $Y$ be sets. Their **union** is the set $X \cup Y$ of all elements that are in at least one of $X$ or $Y$; in set builder notation this is 
$$ X \cup Y = \{\, x \, | \, x \in X \text{ or } x \in Y \}.$$

**Definition 1.3.2.** Let $X$ and $Y$ be sets. Their **intersection** is the set $X \cup Y$ of all elements that are in both $X$ and $Y$; in set builder notation this is 
$$ X \cap Y = \{\, x \, | \, x \in X \text{ and } x \in Y \}.$$

A useful way to visualize combinations of sets is with a Venn diagram. The Venn diagrams for union and intersection are shown below.

PICTURE OF UNION AND INTERSECTION

*Example.* Let $X = \{1,2,3,4\}$ and $Y=\{2,4,7,9\}$. Their union is 
$$ X \cup Y = \{1,2,3,4,7,9\}$$ and their intersection is $$X \cap Y = \{2,4\}.$$ Notice that we do not repeat elements in a set. An element is either in the set or it isn't. (A generalization, the multiset, will be developed in Chapter 11.) Therefore, $|X \cup Y|$ (recall, the number of elements in the union) won't just be $|X|+|Y|$.

**Theorem 1.3.3.** If $X$ and $Y$ are finite sets, then $$|X \cup Y| = |X|+|Y|-|X\cap Y|.$$

*Proof.* If an element is only in $X$, it will be counted by $|X|$. If an element is only in $Y$, it will be counted by $|Y|$. Therefore any elements in $X \cap Y$ will be counted twice. There are exactly $|X \cap Y|$ of these elements, so subtracting that amount gives $|X \cup Y|$. $\square$

**Definition 1.3.4.** Let $X$ and $Y$ be sets. The **difference** $X-Y$ is the set of all elements in $X$ but not $Y$; i.e. $$X-Y=\{ \, x \, | \, x \in X \text{ and } x \not\in Y\}.$$

*Example.* Like before, let $X = \{1,2,3,4\}$ and $Y=\{2,4,7,9\}$. Then $X-Y=\{1,3\}$. Notice that $Y-X=\{7,9\}$; just like with numbers, taking a diference is not **commutative**. (That is, the order matters.)

Often when working with sets there is a **universal** or ambient set, sometimes denoted $\Omega$, that all of our sets are assumed to be subsets of. This set is typically inferred from context. 
* In calculus, this set might be $\mathbf{R}$.
* If my set is "students taking MATH 174," my universal set might be the set of all students at Coastal Carolina.
* In probability theory, the sets are events (e.g. "the roll is odd") and $\Omega$ is the sample space (e.g. all possible rolls of the die). 

**Definition 1.3.5.** Let $X$ be a set contained in some universal set $\Omega$. The **complement** of $X$ (relative to $\Omega$), denoted $\overline{X}$, is all the elements not in $X$. In other words, $\overline{X}=\Omega-X$.

PICTURES OF DIFFERENCES HERE

*Example.* Suppose $X=\{a,b,c\}$ is contained in the universal set $\Omega=\{a,b,c,d,e\}$. Then $\overline{X}=\{d,e\}$.

**Definition 1.3.6.** Let $X$ and $Y$ be sets. Their **Cartesian product** (in this book, just "product") is the set $$X\times Y = \{(x,y)\,|\, x \in X \text{ and } y \in Y\}.$$ The elements of the product are called **ordered pairs.**

As the name implies, the ordering of the entries in an ordered pair matters. Therefore, we will adopt the convention that unordered structures are enclosed in $\{$ curly braces $\}$ and ordered structures are enclosed in $($ parentheses $)$. The immediate consequence to this observation is that $X \times Y$ is different from $Y \times X$.

PICTURE OF CARTESIAN PRODUCT

*Examples.* You are likely familiar with $\mathbf{R}^2=\mathbf{R}\times\mathbf{R}$, the Cartesian plane from algebra and calculus. The elements of this (infinite) set are ordered pairs $(x,y)$ where both $x$ and $y$ are real numbers.

To make a discrete example, put $X=\{a,b,c\}$ and $Y=\{1,2\}$. Then
$$ X \times Y = \{(a, 1), (a,2), (b,1), (b,2), (c,1), (c,2)\}.$$  As an exercise, calculate $Y \times X$ yourself. The pair $(1,a)$ is an element.

**Theorem 1.3.7.** If $X$ and $Y$ are finite sets, then $|X \times Y| = |X||Y|$.

*Proof.* The elements of $X\times Y$ may be tabulated into a rectangle, where each row corresponds to an element of $X$ and each column corresponds to an element of $Y$. There are $|X|$ rows and $|Y|$ columns and therefore $|X||Y|$ elements in the table. $\square$

### 1.4 Operations involving more than two sets

*Note: While this section is cool, we will not make use of its content very often in this course. You may choose to skip this section for now and return to it after Chapter 8, when you are more comfortable with the material.*

There is one last thing to say about sets (for now, anyway). There is no reason to limit ourselves to two sets in union, intersection, and product. If we have a family of $n$ sets $X_1, X_2, \ldots, X_n$, we may take $n$-ary unions, intersections, and products. 

The $n$-ary union $$\bigcup_{i=1}^n X_i = X_1 \cup X_2 \cup \cdots \cup X_n$$ is the set of elements that are in at least one of the sets $X_i$.

The $n$-ary intersection $$\bigcap_{i=1}^n X_i = X_1 \cap X_2 \cap \cdots \cap X_n$$ is the set of elements that are in all of the sets $X_i$.

The $n$-ary product $$\prod_{i=1}^n X_i = X_1 \times X_2 \times \cdots \times X_n$$ is the set of ordered $n$-tuples $(x_1, x_2, \ldots, x_n)$, where the element $x_i$ is a member of the set $X_i$. Such an object may be instead considered as a finite sequence. We will discuss sequences in Chapter 6.

Suppose instead the family $X_1, X_2, \ldots$ is infinite. We will, exactly once in this book, need to take an infinite union. The infinite union $$\bigcup_{i=1}^\infty X_i = X_1 \cup X_2 \cup \cdots $$ is the set of all elements that are in at least one of the $X_i$. (Notice that the definition hasn't changed -- just the number of sets!) Likewise the infinite intersection $$\bigcap_{i=1}^n X_i = X_1 \cap X_2 \cap \cdots $$ is the set of elements in all the $X_i$. An infinite product is better realized as an infinite sequence, which again is the subject of Chapter 6.

## 2. Propositional logic

In mathematics, we spend a lot of time worried about whether a sentence is true or false. This is fine in the case of a simple sentence such as "The number $2$ is prime." (That sentence is true.) But there are much more complicated sentences lurking around, and whole constellations of sentences whose truth depends on one another. (An unsolved problem in mathematics is deciding whether the *Riemann hypothesis*, a statement about the prime numbers, is true. Most people believe it is, and many results in the literature are true given the hypothesis. The Riemann hypothesis is going to make or break a lot of research.)

So, we are interested in tools that will allow us to judge whether complicated statements are true. Such models of truth are called logic.

### 2.1 Statements and connectives

**Definition 2.1.1.** A **statement** is a sentence that is either true or false. 

*Examples.* "The number $2$ is prime" and "It is perfectly legal to jaywalk" are statements. Non-statements include questions ("Is it raining?"), commands ("Do your homework"), and opinions ("Mint chocolate chip ice cream is the superior flavor"). It is important to note, not necessarily for mathematical purposes, that *opinions* are statements of pure taste. Claims whose truth values exist but are unknown are *beliefs*.

**Atomic** propositional statements of the type discussed in this chapter are flatly always true or false. You may think of them in the same way you think of constant functions in algebra. They are denoted with lowercase letters $p$, $q$, $r$, etc. If the only statements were atomic, logic would be boring. Fortunately, we can combine statements with connectives. In the next chapter, we will look at predicate statements whose truth values depend on an input. Likewise, these may be thought of as the non-constant functions.

**Compound** statements arise from combining atomic statements with connectives. They are denoted using Greek letters like $\varphi$ ("phi"), $\psi$ ("psi"), and $\gamma$ ("gamma"). The truth of a **compound** statement depends on the connectives involved and the truth values of the constituent statements. A tool for determining the truth of a compound statement is called a **truth table**. 

In a truth table for the compound statement $\varphi$, the left side of the table is the atomic statements involved in $\varphi$ and the right side of the table is $\varphi$ itself. Each row gives a possible combination of truth values for the atomic statements, and the corresponding truth value for $\varphi$. At this point, it is easier to start introducing connectives and seeing some truth tables.

**Definition 2.1.2.** Let $p$ be a statement. Its **negation** is the statement $\neg p$, the statement that is true exactly when $p$ is false and vice-versa. 

The statement $\neg p$ is typically read "not $p$" or "it is not the case that $p$ is true." If we have an English rendering of $p$, we try to write $\neg p$ in a natural-sounding way that also conveys its logical structure. 

*Example.* Suppose $p$ represents the statement "It is raining." Then, $\neg p$ stands for "It is not raining."

Below is the truth table for $\neg p$.

|$p$|$\neg p$|
|--|--|
|$T$|$F$|
|$F$|$T$|

As you can see, on the left are columns corresponding to the atomic statements involved in $\neg p$ (just $p$), and each row is a possible combination of truth values for these statements. Here is a quick, useful theorem without proof:

**Theorem 2.1.3.** If the compound statement $\varphi$ involves $n$ different atomic statements, then its truth table has $2^n$ rows.

Look familiar? We will prove this theorem when we prove the related theorem about power sets later on.

Negation is called a **unary** connective because it only involves one statement. Our remaining connectives are all **binary** connectives, as they combine two statements.

**Definition 2.1.4.** Let $p$ and $q$ be statements. Their **conjunction** is the statement $p \wedge q$, which is true only when $p$ and $q$ are both true.

The symbol in the conjunction is called a "wedge," and $p \wedge q$ is read "$p$ and $q$." This definition is meant to be analogous to our English understanding of the word "and." The statements $p$ and $q$ are called **conjuncts**.

*Example.* Letting $p$ be "It is raining" and $q$ be "I brought an umbrella," the statement $p \wedge q$ is "It is raining and I brought an umbrella." The statement is true only if it is currently raining and the speaker brought an umbrella. If it is not raining, or if the speaker did not bring their umbrella, the conjunction is false.

Here is the truth table for $p \wedge q$:

|$p$|$q$|$p \wedge q$  |
|--|--|--|
| $T$ | $T$ | $T$|
| $T$ | $F$ | $F$|
| $F$ | $T$ | $F$|
|$F$|$F$|$F$|

Notice that this table is organized intentionally, not haphazardly. The rows are divided into halves, where $p$ is true in one half and then false in the other half. The rows where $p$ is true are further subdivided into half where $q$ is true and half where $q$ is false. If there were a third letter, we would subdivide the rows again, and so on. This method of organizing the truth table allows us to ensure we did not forget a row. Our leftmost atomic letter column will always be half true followed by half false, and the rightmost atomic letter column will always alternate between true and false.

**Definition 2.1.5.** Let $p$ and $q$ be statements. Their **disjunction** is the statement $p \vee q$, which is true if at least one of $p$ or $q$ is true.

The symbol in the conjunction is called a "vee" and $p \vee q$ is read "$p$ or $q$." This definition is meant to be analogous to our English understanding of the word "or." The statements $p$ and $q$ are called **disjuncts**. (Did you notice that I was able to copy and paste from an above paragraph? Conjunction and disjunction share a very similar structure.)

*Example.* Letting $p$ be "It is raining" and $q$ be "I brought an umbrella," the statement $p \vee q$ is "It is raining or I brought an umbrella." This time, the speaker only needs to meet one of their conditions. They are telling the truth as long as it is raining or they brought an umbrella, or even if both statements are true.

The truth table for $p \vee q$ follows.

|$p$|$q$|$p \vee q$  |
|--|--|--|
| $T$ | $T$ | $T$|
| $T$ | $F$ | $T$|
| $F$ | $T$ | $T$|
|$F$|$F$|$F$|

Of great importance to computer science and electrical engineering, but not so much in mathematics (so it will not appear again in this book), is the exclusive disjunction (or "exclusive-or"). It is a modified disjunction where *exactly* one of the disjuncts must be true.

**Definition 2.1.6.** If $p$ and $q$ are statements, their **exclusive disjunction** is the statement $p \oplus q$, which is true if and only if exactly one of $p$ and $q$ is true.

The statement $p \oplus q$ is read "$p$ exclusive-or $q$." 

*Example.* The statement "You can have the soup or the salad" is likely meant as an exclusive disjunction.

In mathematics, disjunctions are generally considered inclusive unless stated otherwise. (An example for us all to follow!)

Our next connective is probably the most important, as it conveys the idea of one statement implying another. As we discussed earlier in the chapter, mathematics is nothing but such statements. It is also the only connective that is not relatively easy to understand given its English interpretation. So we will begin with the truth table, and think carefully about each row.

**Definition 2.1.7.** If $p$ and $q$ are statements, the **conditional statement** $p \to q$ is true if $p$ can never be true while $q$ is false.

There are many ways to read $p \to q$, including "if $p$, then $q$," "$p$ implies $q$", and "$p$ is sufficient for $q$." The statement before the arrow is the **antecedent** and the following statement is the **consequent**. Here is the conditional's truth table.

|$p$|$q$|$p \to q$  |
|--|--|--|
| $T$ | $T$ | $T$|
| $T$ | $F$ | $F$|
| $F$ | $T$ | $T$|
|$F$|$F$|$T$|

That $p \to q$ is true in the bottom two rows may surprise you. So, let's consider each row separately.

*Example.* Let $p$ be "You clean your room" and $q$ be "I will pay you $10," so that $p\to q$ is "If you clean your room, then I will pay you $10."

In the case that both $p$ and $q$ are true, the speaker has told the truth. You cleaned, and you were paid. All is well.

In the case that $p$ is true but $q$ is false, the speaker has lied. You cleaned the room, but you did not earn your money.

What if $p$ is false? Well, then the speaker did not lie. The speaker said that *if* you clean your room you will be paid. If the room isn't cleaned, then $p \to q$ cannot be falsified, no matter where $q$ is true or false.

If that explanation is not sufficient for you, reread the definition of the conditional: $p \to q$ being true *means* that $p$ cannot be true without $q$. If you are unsatisfied by the English connection, then consider $p \to q$ to be a purely formal object whose definition is the above truth table.

**Definition 2.1.8.** If $p$ and $q$ are statements, the **biconditional statement** $p \leftrightarrow q$ is true if $p$ and $q$ are both true, or both false.

The statement $p \leftrightarrow q$ may be read as "$p$ if and only if $q$, "$p$ is necessary and sufficient for $q$," or "$p$ is equivalent to $q$." Here is the truth table.
|$p$|$q$|$p \to q$  |
|--|--|--|
| $T$ | $T$ | $T$|
| $T$ | $F$ | $F$|
| $F$ | $T$ | $F$|
|$F$|$F$|$T$|

*Example.* Let $p$ be "You clean your room" and $q$ be "I will pay you $10," so that $p\leftrightarrow q$ is "I will give you $10 if and only if you clean your room." (The statements were reordered for readability. We will see later in the chapter that this is the same statement, but this wouldn't work for $p \to q$.) This time, the clean room and the $10 paycheck are in total correspondence; one doesn't happen without the other.

### 2.2 Connecting connectives

We are not required to use one connective at a time, of course. Most statements involve two or more connectives being combined at once. If $\varphi$ and $\psi$ are statements, then so are: $\neg \varphi$, $\varphi \wedge \psi$, $\varphi \vee \psi$, $\varphi \to \psi$, and $\varphi \leftrightarrow \psi$. This fact allows us to combine as many connectives and statements as we like.

How should we read the statement $p \wedge q \to r$? Should it be read "$p$; also, if $q$ then $r$"? Or, "If $p$ and $q$, then $r$?" Just like with arithmetic, there are conventions defining which connective to apply first: negation, then conjunction/disjunction, then implication, then bi-implication. So, "If $p$ and $q$, then $r$" is correct. However, to eliminate confusion in this book we will always use parentheses to make our statements clear. Therefore, we would write this statement as $(p \wedge q) \to r$.

Remember that a statement involving $n$ letters will have $2^n$ rows in its truth table. The column for the left-most statement letter should be true for half the rows then false for half the rows, and you should continue dividing the rows in half so that the right-most statement letter's column is alternating between true and false.

Finally, it is a good idea to break a statement into small "chunks" and make a column for each "chunk" separately. Observe the following example.

*Example.* Write down the truth table for the statement $(p \wedge q) \to (r \to \neg s)$. When is this statement false?

Since the statement has $4$ letters, there will be $2^4=16$ rows to the truth table. Let's go through the first row very slowly, where all four atomic statements are true. Then $p \wedge q$ is true and $\neg s$ is false. Since $r$ is true and $\neg s$ is false, that means $r \to \neg s$ is false. Finally, because its antecedent is true and its consequent is false, the compound statement $(p \wedge q) \to (r \to \neg s)$ would be false.

Here is the full truth table. Be sure you understand how each row is calculated.


|$p$|$q$|$r$|$s$|$p \wedge q$  |$\neg s$|$r \to \neg s$|$(p \wedge q) \to (r \to \neg s)$
|--|--|--|--|--|--|--|--|
| $T$ | $T$ | $T$|$T$|$T$ |$F$ |$F$ |$F$ |
| $T$ | $T$ | $T$|$F$|$T$ |$T$ |$T$ |$T$ |
| $T$ | $T$ | $F$|$T$|$T$ |$F$ |$T$ |$T$ |
| $T$ | $T$ | $F$|$F$|$T$ |$T$ |$T$ |$T$ |
| $T$ | $F$ | $T$|$T$|$F$ |$F$ |$F$ |$T$ |
| $T$ | $F$ | $T$|$F$|$F$ |$T$ |$T$ |$T$ |
| $T$ | $F$ | $F$|$T$|$F$ |$F$ |$T$ |$T$ |
| $T$ | $F$ | $F$|$F$|$F$ |$T$ |$T$ |$T$ |
| $F$ | $T$ | $T$|$T$|$F$ |$F$ |$F$ |$T$ |
| $F$ | $T$ | $T$|$F$|$F$ |$T$ |$T$ |$T$ |
| $F$ | $T$ | $F$|$T$|$F$ |$F$ |$T$ |$T$ |
| $F$ | $T$ | $F$|$F$|$F$ |$T$ |$T$ |$T$ |
| $F$ | $F$ | $T$|$T$|$F$ |$F$ |$F$ |$T$ |
| $F$ | $F$ | $T$|$F$|$F$ |$T$ |$T$ |$T$ |
| $F$ | $F$ | $F$|$T$|$F$ |$F$ |$T$ |$T$ |
| $F$ | $F$ | $F$|$F$|$F$ |$T$ |$T$ |$T$ |

There are tricks to calculate truth tables more efficiently. However, it wouldn't do you any good to read them; they must come with practice.

### 2.3 Inference and equivalence 
