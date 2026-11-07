# The attack prompt

Generic form; in practice it is one file in the brain, filled by the runner with literal values. From Appendix B of *Give Your AI Agents a Brain*.

```
Produce realistic adversarial inputs for the rules in <spec section>, as fixtures with expected outputs, not commentary. Each fixture: what it stresses, why it is needed, the real-shaped input, the expected result, and your reading of the rule. No real people; no input copied from a real record. Run each read-only against <commit> and report which pass and which fail as written. The owner approves each fixture before it enters the fixture set; a reading that contradicts a written rule becomes a ruling, not a fixture.
```
