
<p>
Start by exploring the fundamental concepts by interacting with the basic operations 
available in the tool.
</p>

<p>
Select any basic operation to view its corresponding 
<strong>NFA graphical representation</strong> along with the equivalent 
<strong>Regular Expression</strong>.
</p>

<h4>Step 1 – Define States</h4>
<p>
Begin by creating or confirming the <strong>states</strong> of your NFA.  
Mark one state as the <strong>Start</strong> state and at least one as the 
<strong>Accepting</strong> state.
</p>
<img src="./images/Step1Nfa.png" alt="Step 1 – Define States" style="max-width:100%; height:auto; margin-top:16px;">

<h4>Step 2 – Configure NFA</h4>
<p>
Once the states are set, review the automatically generated transitions.  
When everything is ready, click the <strong>Convert to Regular Expression</strong> 
button to begin the process.
</p>
<img src="./images/Step2Select.png" alt="Step 2 – Configure NFA" style="max-width:100%; height:auto; margin-top:16px;">

<h4>Step 3 – State Elimination</h4>
<p>
The tool will now guide you through <strong>state elimination</strong>.  
Intermediate states are removed one by one while updating transitions to 
preserve possible paths.  
Continue this until only the Start and Final states remain.
</p>
<ol>
  <li>Select a state to remove.</li>
  <li>Click <strong>Remove Selected</strong>.</li>
  <li>Repeat until just the initial and final nodes remain.</li>
</ol>
<p>
💡 <em>Tip:</em> Start by removing states with fewer transitions 
to simplify the resulting expression.
</p>
<img src="./images/Step3Convert.png" alt="Step 3 – State Elimination" style="max-width:100%; height:auto; margin-top:16px;">

<h4>Step 4 – Final Regular Expression</h4>
<p>
Once all intermediate states are removed, the edge between the Start and Final 
nodes will represent the complete <strong>Regular Expression</strong> corresponding 
to the original NFA.
</p>
<p>
✅ <b>Conversion Complete!</b>
</p>
<img src="./images/Step5Final.png" alt="Step 4 – Final Regular Expression" style="max-width:100%; height:auto; margin-top:16px;">
