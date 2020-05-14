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

[PICTURES: UNION AND INTERSECTION]

*Example.* Let $X = \{1,2,3,4\}$ and $Y=\{2,4,7,9\}$. Their union is 
$$ X \cup Y = \{1,2,3,4,7,9\}$$ and their intersection is $$X \cap Y = \{2,4\}.$$ Notice that we do not repeat elements in a set. An element is either in the set or it isn't. (A generalization, the multiset, will be developed in Chapter 11.) Therefore, $|X \cup Y|$ (recall, the number of elements in the union) won't just be $|X|+|Y|$.

**Theorem 1.3.3.** If $X$ and $Y$ are finite, then $$|X \cup Y| = |X|+|Y|-|X\cap Y|.$$

*Proof.* If an element is only in $X$, it will be counted by $|X|$. If an element is only in $Y$, it will be counted by $|Y|$. Therefore any elements in $X \cap Y$ will be counted twice. There are exactly $|X \cap Y|$ of these elements, so subtracting that amount gives $|X \cup Y|$. $\square$




