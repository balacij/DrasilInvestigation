ICO refers to a straightforward kind of software: calculators. These calculators strictly have 3 components:
* Accepting/reading in user-provided input variables.
* Performing calculations based on said inputs and intermediate variables.
* Outputting desirable output variables for the user to consume.
## Example: Hello $X$

```python
name = input("What's your name?")
out_msg = f"Hello {name}!"
print(out_msg)
```

This is the simplest kind of ICO software. The inputs are $\set{\texttt{name}}$ and the outputs are $\set{\texttt{out\_msg}}$. The only calculation performed places the input $\texttt{name}$ into a string template welcome message.

## Example: Drasil's Case Studies

The majority of [[Drasil]]'s case studies at the moment are simple ICO-style software. For example, [[Projectile]].