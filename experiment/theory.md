<u><h3>Theory</h3></u>
<h5>Non-Deterministic Finite Automata(NFA) </h5>

<p>
A Nondeterministic Finite Automaton (NFA) is a theoretical machine used in formal language theory to recognize regular languages. 
It is defined as a 5-tuple:<p> <em>NFA = (Q, Σ, δ, q₀, F)</em></p> where:
</p>
<ul>
  <li><strong>Q</strong> is a finite set of states</li>
  <li><strong>Σ</strong> is a finite input alphabet</li>
  <li><strong>δ</strong> is the transition function: <em>δ: Q × (Σ ∪ {ε}) → 2^Q</em></li>
  <li><strong>q₀</strong> ∈ Q is the initial (start) state</li>
  <li><strong>F</strong> ⊆ Q is the set of accepting (final) states</li>
</ul>
<p>
In an NFA, the transition function allows multiple possible next states for a given input, including transitions on the empty string (ε). 
A string is accepted if at least one computation path leads from the start state to a final state while consuming the entire input.
</p>

<h5> Regular Expressions</h5>

<p>
A Regular Expression (RE)is a symbolic representation used to describe a regular language. 
It defines a set of strings over a given alphabet using specific operators and rules.
</p>
<p>
Regular expressions are built using:
</p>
<ul>
  <li><strong>Union (|):</strong> Represents a choice between expressions. For example, <em>a|b</em> matches either "a" or "b".</li>
  <li><strong>Concatenation:</strong> Represents sequences. For example, <em>ab</em> matches "a" followed by "b".</li>
  <li><strong>Kleene Star (*):</strong> Represents repetition (zero or more times). For example, <em>a*</em> matches "", "a", "aa", "aaa", etc.</li>
</ul>
<p>
A regular expression describes the same class of languages that can be recognized by finite automata. 
Thus, for every regular expression, there exists an equivalent NFA that accepts the same language, and vice versa.
</p>

<p>
In this experiment, we use the <strong>State Elimination Method</strong> to convert a given 
<strong>Nondeterministic Finite Automaton (NFA)</strong> into an equivalent 
<strong>Regular Expression (RE)</strong>. This method is widely used due to its systematic 
and intuitive approach for eliminating states and building up the corresponding expression.
</p>
<p><strong>State Elimination Method</strong> </p>
<p>
The State Elimination Method involves simplifying the NFA step-by-step by removing intermediate 
states while preserving the language accepted by the automaton. At each step, transitions between 
the remaining states are updated using regular expressions that represent the combined paths.
</p>
<p>
The process generally includes the following steps:
</p>
<strong><p>Step-1:</p></strong>
<p>If there are incoming transitions to the initial state:</p>
<li>Create a new start state with no incoming edges.</li>
<li>Add an outgoing edge from the new start state to the old start state with an ε-transition.</p>
<li>The initial state before is now a normal state with an added incoming ε-transition.
<div><img src="./images/rule1.png" alt="types of method"></div>
<strong><p>Step-2:</p></strong>
<p>If there are outgoing transitions from the final state:</p>
<li>Create a new final state with no outgoing edges.</li>
<li>Add an incoming edge to the new final state from the old final state with an ε-transition.</li>
<li>The old final state is transformed into a normal state with the added transition of ε.</li>
<div><img src="./images/rule2.png" alt="types of method"></div>
<strong><p>Step-3:</p></strong>
<p>If the automaton has multiple final states:</p>
<li>Remove the final state  from the multiple final states.</li>
<li>Add outgoing ε-transitions from the multiple final states to a new and only final state with no outgoing transitions.</li>
<div><img src="./images/rule3.png" alt="types of method"></div>
<strong><p>Step-4:</p></strong>
Eliminate all the states one by one except initial state and final state to get the final result which is the regular expression for the given NFA 
