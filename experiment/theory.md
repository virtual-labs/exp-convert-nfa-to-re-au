<h3>Theory</h3>

<h5>Non-Deterministic Finite Automata (NFA)</h5>
<p>
A <strong>Nondeterministic Finite Automaton (NFA)</strong> is a theoretical machine used in 
formal language theory to recognize <strong>regular languages</strong>. 
It is defined as a 5-tuple:
</p>
<p><em>NFA = (Q, Σ, δ, q₀, F)</em></p>
<ul>
  <li><strong>Q</strong> → finite set of states</li>
  <li><strong>Σ</strong> → finite input alphabet</li>
  <li><strong>δ</strong> → transition function, <em>δ: Q × (Σ ∪ {ε}) → 2^Q</em></li>
  <li><strong>q₀</strong> ∈ Q → initial state</li>
  <li><strong>F</strong> ⊆ Q → set of accepting (final) states</li>
</ul>
<p>
In an NFA, multiple next states may exist for the same input, including 
<em>ε-transitions</em>. A string is accepted if at least one computation 
path leads from <strong>q₀</strong> to a final state in <strong>F</strong> after consuming the entire input.
</p>

<h5>Regular Expressions</h5>
<p>
A <strong>Regular Expression (RE)</strong> is a symbolic representation used to 
describe a <strong>regular language</strong>. Regular expressions use operators such as:
</p>
<ul>
  <li><strong>Union (|)</strong>: choice (e.g., <em>a|b</em> → "a" or "b")</li>
  <li><strong>Concatenation</strong>: sequence (e.g., <em>ab</em> → "a" followed by "b")</li>
  <li><strong>Kleene Star (*)</strong>: repetition (e.g., <em>a*</em> → "", "a", "aa", …)</li>
</ul>
<p>
Every regular expression corresponds to an NFA, and every NFA can be converted into 
an equivalent RE. In this experiment, we apply the <strong>State Elimination Method</strong>.
</p>

<h5>State Elimination Method</h5>
<p>
The <strong>State Elimination Method</strong> converts an NFA into an equivalent 
RE by systematically removing states while preserving the accepted language. 
When only the <strong>start state</strong> and a 
<strong>final state</strong> remain, the label on the direct edge between them 
represents the final RE.
</p>

<h5>Algorithm</h5>
<ol>
  <li><strong>Standardize the NFA</strong>:
    <ul>
      <li>If the start state has incoming transitions, create a <em>new start state</em> 
          with an <em>ε-transition</em> to the old start state.</li>
      <li>If there are multiple final states, create a <em>new final state</em> and connect 
          all old final states to it using <em>ε-transitions</em>.</li>
    </ul>
  </li>

  <li><strong>Elimination of states</strong> (core step):
    <p>For each intermediate state <em>R</em> (not start or final):</p>
    <ul>
      <li>Let <em>P</em> = set of predecessor states of R.</li>
      <li>Let <em>S</em> = set of successor states of R.</li>
      <li>For every <em>(p, R)</em> and <em>(R, s)</em> path:
        <ul>
          <li>If there is a loop on R labeled <em>r<sub>RR</sub></em>, include <em>(r<sub>RR</sub>)*</em>.</li>
          <li>Update the transition from <em>p → s</em> as:
            <p style="margin-left:20px;"><em>
              r<sub>ps</sub> = r<sub>ps</sub> | (r<sub>pR</sub>(r<sub>RR</sub>)*r<sub>Rs</sub>)
            </em></p>
            (where <em>r<sub>ps</sub></em> is the existing label on edge p→s).
          </li>
        </ul>
      </li>
      <li>Remove state R from the automaton.</li>
    </ul>
  </li>

  <li><strong>Repeat</strong> until only the start state and final state remain.</li>

  <li><strong>Final Expression</strong>:
    <p>
    The label on the edge from the start state to the final state is the required 
    <strong>Regular Expression</strong>.
    </p>
  </li>
</ol>

<h5>Illustration</h5>
<p>
For example, consider an NFA with states Q = {q0, q1, q2}, where q0 is the start 
state and q2 is the final state. By applying elimination to q1, we rewrite transitions and finally 
obtain the RE for the language accepted by the automaton.
</p>
