Download Link: https://assignmentchef.com/product/solved-ceng462-homework-2
<br>
This assignment aims to assist you to expand your knowledge on First Order Predicate Logic.

<h2>2       Problem Definition</h2>

In this assignment, you are going to implement a function called theorem prover in python as a theorem prover for First Order Predicate Logic by using <em>Resolution Refutation </em>technique and <em>Linear Input Strategy </em>in the <em>written order </em>of clauses. This function gets two lists of clauses in <em>Conjunctive Normal Form (CNF)</em>, namely the list of base clauses and the list of clauses obtained from the negation of the theorem.

Your program has to eliminate

<ul>

 <li>tautologies</li>

 <li>subsumptions in the case of a resolution.</li>

</ul>

The function detects whether the theorem is derivable or not. Then, it returns the result as a tuple. First element of this tuple will be “yes” or “no” according to derivability of the theorem. The second element will be <strong>list of all resolutions </strong>that are processed during the search of proof. Further details about the return value can be seen in the following sections.

<h2>3       Specifications</h2>

<ul>

 <li>As Linear Input Strategy indicates, at least one parent must be selected from the <strong>initial base set of clauses </strong>(<em>the given list of base clauses together with the negation of the theorem</em>) while processing a resolution.</li>

 <li>By the convention we follow in FOPL; variables, predicate and function names start with with a lower case letter, while the names of the constants start with an upper case letter. <strong>Note that none of these does not have to be a one-letter name.</strong></li>

</ul>

1

<ul>

 <li>In the given clauses; “+” and “!” signs will be used for disjunction and negation respectively.</li>

 <li>Each resolution in the return value must be given in “<em>&lt; clause</em>1 <em>&gt; </em>$ <em>&lt; clause</em>2 <em>&gt; </em>$ <em>&lt; resolvent &gt;</em>” form <strong>without using any space character</strong>.</li>

 <li>The “empty” string must be used for empty clause in the return value.</li>

</ul>

<h2>4        Sample Function Calls</h2>

&gt;&gt;&gt; theorem_prover([“p(A,f(t))”, “q(z)+!p(z,f(B))”, “!q(y)+r(y)”],[“!r(A )”])

(’yes’, [’p(A,f(t))$q(z)+!p(z,f(B))$q(A)’, ’q(A)$!q(y)+r(y)$r(A)’, ’r(A) $!r(A)$empty’])

&gt;&gt;&gt; theorem_prover([“p(A,f(t))”, “q(z)+!p(z,f(B))”, “q(y)+r(y)”],[“!r(A) “])

(’no’, [’p(A,f(t))$q(z)+!p(z,f(B))$q(A)’, ’q(y)+r(y)$!r(A)$q(A)’])