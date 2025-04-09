The Projectile [[SystemInformation]] (SI) defines what "[[Projectile]]" means. Unfortunately, SI is not a [[well-understood]] data type in Drasil. Thus, we will try to excavate some meaning by deconstructing Projectile's SI (sorted according to deconstructing):

```haskell
si :: SystemInformation
si = SI {
  _kind        = Doc.srs,
  _sys         = projectileTitle,
  _authors     = [samCrawford, brooks, spencerSmith],
  _motivation  = [motivation],
  _background  = [background],
  _purpose     = [purp],
  _inputs      = inputs,
  _outputs     = outputs,
  _scope       = [scope],
  _constants   = constants,
  _constraints = map cnstrw constrained,
  _quants      = symbols,
  _datadefs    = dataDefs,
  _instModels  = iMods,
  _sysinfodb   = symbMap,
  _usedinfodb  = usedDB,
  _configFiles = []
}
```

## Deconstructing Projectile's SI

In this subsection, we will examine each sections of the above code snippet according to how I see it being logically connected. The order is as follows:
* [[#Intention to Define a Software Requirements Specification]].
* [[#Defining an Input-Calculate-Output (ICO) Software Solution (an Abstract Software Solution) for Software Generation]]
* [[#Remaining SI Components]]

### Intention to Define a Software Requirements Specification.

```haskell
si :: SystemInformation
si = SI {
  _kind        = Doc.srs,
```

* `Doc.srs` is a [[CI]] with a `UID` ("srs"), term ("[[Software Requirements (IdeaDict)|software requirements]] [[Specification (IdeaDict)|specification]]"), abbreviation ("SRS"), and a "concept domain" ([[Software Engineering (IdeaDict)|software engineering]]).

The first thing the SI contains is a "notice" -- that we are interested in modelling a software computation problem, using standard/conventional terminology. I say "notice" because the only indication of this notice is `_kind`, filled in by `Doc.srs`, a [[CI]] (a "common idea" chunk, defining the acronym "SRS" ([[Software Requirements Specification (CI)]]) and its long form with no other semantic information). All of Drasil's other case studies also use `Doc.srs`, except for the [[Projectile Lesson Plan]] (PLP). PLP defines a `Doc.notebook` and uses very few of the remainder of the SI field. Thus `_kind` may mean something more than a what a simple [[CI]] conveys.

I believe the SRS in question also *implicitly* refers to the SmithEtAl SRS template ([[SmithAndLai2005]]) because that brings about the terminology we use in organizing scientific knowledge in Drasil (e.g., [[TheoryModel]], [[InstanceModel]], etc.). It also brings about some of our presumed nonfunctional requirements: traceable, correct, and verifiable (not necessarily: reusable, understandable, maintainable, and portable).

In defining an SRS, we are defining (1) an abstract software solution ([[#Defining an Input-Calculate-Output (ICO) Software Solution (an Abstract Software Solution) for Software Generation]]) to a (2) specific mathematical problem ([[#Defining the Mathematical Problem First]]). Our capture of this information (that we're presenting a software problem nor an abstract solution) is scattered across bits and pieces of Drasil's codebase. `drasil-docLang` contains much of that. Should we enrich the `Doc.srs` [[CI]], these two pieces of information should be related under the `Doc.srs` hat.

Returning to the point of "the SI defines 'Projectile'," "Projectile" is evidently overloaded. Does it refer to the software requirements? The specific mathematical problem? The stuff we intend to generate with the SI? All? The first two? I'm not sure.

### Defining an [[Input-Calculate-Output (ICO)]] Software Solution (an Abstract Software Solution) for Software Generation

The implicit software problem is an ICO style computation software. In the case of the SI, we're heavily specialized to Drasil's existing case studies, but it should be more general, and thus we can and should refer to this as an "abstract software/solution" (AS; which is approximately the same as a "software requirements specification"). Before defining the AS, we need to define what the AS is a _solution for_ (i.e., what the problem is).

<div style="background: rgba(255, 255, 0, 0.3);">
  <b>Note</b>: The "ICO" part of the SI is implicit. There is no word that specifically ties together the fields discussed here under an "ICO" hat.
</div>

#### Defining the Mathematical Problem First

The problem has two components to it:
1. Meta-information (containing background information about the problem, sources for the problem, authorship, etc.).
2. A comprehensive mathematical description of the problem.
 
##### Problem Meta-information

The metainformation for the calculation problem begins with: a title, authors, and rationale for why bothering with encoding this at all. Yes, the title is metainformation. The relevant parts of the SI are as follows:

```haskell
  _sys         = projectileTitle,
  _authors     = [samCrawford, brooks, spencerSmith],
  _motivation  = [motivation],
  _background  = [background],
```

Excavating further:
* `projectileTitle` is a [[CI]] with a UID (`projectileTitle`), term (a proper noun: `"Projectile"`), and an abbreviation ("Projectile").
* `[samCrawford, brooks, spencerSmith]` is a list of `Person`s, each with a "Western" name set as the "kind" for each of he authors.
* `motivation` is a [[Sentence]] encoding "[[Projectile (ConceptChunk)|Projectile]] [[motion (ConceptChunk)|motion]] is a common [[problem (IdeaDict)|problem]] in [[Physics (IdeaDict)]]."
* `background` is a [[Sentence]] encoding "Common examples of [[Projectile (ConceptChunk)|projectile]] [[motion (ConceptChunk)|motion]] include ballistics [[problem (IdeaDict)|problem]]s (missiles and bullets) and the flight of the balls in various sports (baseball, golf, football, etc.)."

This meta-information implicitly explains why building a software for this software problem is justified, and gives rationale for building this specific software.





I believe this metainformation also implicitly brings about the "Characteristics of the Intended Reader" into scope as well, bringing about what DSLs, terms (terminology in general), theories, etc. are relevant to us and into scope. We don't explicitly have this written down anywhere, but it brings about the swath of theory needed to possibly discuss the mathematical description of the problem (e.g., what is a position, what is 2D collision, what is a launcher/cannon, target, and projectile, what are the kinematics equations, etc.). All of these need to be defined _before_ we can even create the meta-information. For example, `Projectile`, `motion`, and `physics` are presumed at this level and are expected to be used in the [[#Mathematical Description]].





##### Mathematical Description

The mathematical description defines a specific calculation problem (knowns/unknowns). Here, that specific calculation problem is the "Projectile target hit estimator/calculator." This is formed by the following code:

```haskell
  _purpose     = [purp],
  _inputs      = inputs,
  _outputs     = outputs,
```
* `purp` is a [[Sentence]] encoding "Predict whether a launched [[Projectile (ConceptChunk)|projectile]] hits its [[target (ConceptChunk)|target]]" (i.e., an English description of the common physics knowns/unknowns problem for which the software would be helpful for solving).
* `inputs` is a list of three [[QuantityDict]]s extracted from [[ConstrConcept]]s: [[launch speed (ConstrConcept)|launch speed]], [[launch angle (ConstrConcept)|launch angle]], and [[target position (ConstrConcept)|target position]].
* `outputs` is a list of three [[QuantityDict]]s: [[message (QuantityDict)|message]] and two extracted from [[ConstrConcept]]s: [[offset (ConstrConcept)|offset]] and [[flight duration (ConstrConcept)|flight duration]].

This mathematical problem description does not imply a solution exists. However, it implies a problem where there is some unknown function $f$ such that $f(inputs)=outputs$. It only defines an abstract problem. The specific problem and specific solution are defined the abstract software.

#### Returning to the Abstract Software (AS)

 Finally, we can return to the abstract software/solution. Abstract here is in the sense that it is a model for a software family. From another point of view, it is a concrete solution to an abstract mathematical problem because it needs to contain enough information such that a human could use its knowledge to calculate solutions for specific inputs on their own.

To define the abstract solution, we carve out a scope (assumptions) for which we can define $f$. As per the Smith et al template, this also means defining $f$ from sound theory. This may mean a few things:

- That we're only looking to carve out a solution for a subset of the inputs. Perhaps because the problem is too generic and is unknown for many input combinations.
- That we need more inputs to solve this or want to add more inputs to future-proof the software. We don't do this in Projectile, but we could easily have a default gravitational acceleration constant (e.g., Earth's $9.81m/s^2$) that becomes an input variable.
- That we add extra outputs (e.g., because we have intermediate variables of interest to users of the software and want to spit out debug information, or that we want to add pretty output messages).

The abstract software is defined by the following record items:
```haskell
  _scope       = [scope],
  _constants   = constants,
  _constraints = map cnstrw constrained,
  _quants      = symbols, -- _All_ relevant variables (including immediate variables).
  _datadefs    = dataDefs, -- "Let" bindings of variables (?).
  _instModels  = iMods,
```
* `scope` is a [[Sentence]] encoding "The [[analysis (IdeaDict)|analysis]] of a [[two-dimensional (CI)|two-dimensional]] (2D), [[Projectile (ConceptChunk)|projectile]] [[motion (ConceptChunk)|motion]] [[problem (IdeaDict)|problem]] with [[constant acceleration (UnitalChunk)|constant acceleration]]" (i.e., an English summary of the scope the solution is relevant to).
* `constants` is a list of constant variable assumptions ([[ConstQDef]]s): [[gravitational acceleration (ConstQDef)|gravitational acceleration]], [[pi (ConstQDef)|pi]], and a [[tolerance (ConstQDef)|tolerance]].
* `constraints` is a list of [[ConstrainedChunk]]s extract from [[ConstrConcept]]s: [[flight duration (ConstrConcept)|flight duration]], [[landing position (ConstrConcept)|landing position]], [[launch angle (ConstrConcept)|launch angle]], [[launch speed (ConstrConcept)|launch speed]], [[offset distance (ConstrConcept)|offset distance]], and [[target position (ConstrConcept)|target position]]. This imposes constraints on any variables. For example, if the abstract solution were only relevant to a subset of the input domain, we could impose the restriction with constraints placed on the input symbols.
* `quants` is a list of all relevant variables to the solution (as [[QuantityDict]]s). All but [[message (QuantityDict)]] are extracted from other things, including:
	* [[ConstQDef]]s:
		* [[gravitational acceleration (ConstQDef)|gravitational acceleration]],
		* [[pi (ConstQDef)|pi]], and
		* [[tolerance (ConstQDef)|tolerance]].
	* [[ConstrConcept]]s:
		* [[flight duration (ConstrConcept)|flight duration]],
		* [[landing position (ConstrConcept)|landing position]],
		* [[launch angle (ConstrConcept)|launch angle]],
		* [[launch speed (ConstrConcept)|launch speed]],
		* [[offset distance (ConstrConcept)|offset distance]], and
		* [[target position (ConstrConcept)|target position]].
	* [[UnitalChunk]]s:
		* [[acceleration (UnitalChunk)|acceleration]],
		* [[constant acceleration (UnitalChunk)|constant acceleration]],
		* [[initial position (UnitalChunk)|initial position]],
		* [[initial speed (UnitalChunk)|initial speed]],
		* [[initial velocity (UnitalChunk)|initial velocity]],
		* [[x-component of initial position (UnitalChunk)|x-component of initial position]],
		* [[y-component of initial position (UnitalChunk)|y-component of initial position]],
		* [[x-component of initial velocity (UnitalChunk)|x-component of initial velocity]],
		* [[y-component of initial velocity (UnitalChunk)|y-component of initial velocity]],
		* [[position (UnitalChunk)|position]],
		* [[scalar position (UnitalChunk)|scalar position]],
		* [[1D position (UnitalChunk)|1D position]],
		* [[1D speed (UnitalChunk)|1D speed]],
		* [[time (UnitalChunk)|time]],
		* [[velocity (UnitalChunk)|velocity]],
		* [[x-component of acceleration (UnitalChunk)|x-component of the acceleration]],
		* [[x-component of constant acceleration (UnitalChunk)|x-component of the constant acceleration]],
		* [[x-component of position (UnitalChunk)|x-component of the position]],
		* [[x-component of velocity (UnitalChunk)|x-component of the velocity]],
		* [[y-component of acceleration (UnitalChunk)|y-component of acceleration]],
		* [[y-component of constant acceleration (UnitalChunk)|y-component of constant acceleration]],
		* [[y-component of position (UnitalChunk)|y-component of position]], and
		* [[y-component of velocity (UnitalChunk)|y-component of velocity]].
* `iMods` is a list of the [[InstanceModel]]s relevant to Projectile. These implicitly form a system of equations that can be solved to calculate the output variables. Rather, for code generation to work, these [[InstanceModel]]s need to form a system of equations such that this is possible. We will return to this shortly. 
  <div style="background: rgba(255, 255, 0, 0.3);"><b>Note</b>: The calculation scheme may have "holes" that need to be filled in by the code generator. For example, ODEs need choices to be made about which method/library to use.</div>

* Unfortunately, `_inputs` and `_outputs` are not divided into two lists each (one containing purely the abstract problem inputs/outputs, and the other containing the specific inputs/outputs the software solution schematic will actually work with). However, if they were, the below items might be moved here:
	* `inputs`: no change, or possibly the constants moved into optional inputs.
	* `outputs`: [[message (QuantityDict)]].

At this point, everything necessary for a software generator to be defined and configured (to generate a solution for the Projectile problem) is here and ready. Returning to the system of equations formed by the [[InstanceModel]]s, the following is the calculation scheme:

1. By [[Calculation of landing time (InstanceModel)]], we define [[flight duration (ConstrConcept)]] as:
	$$
	{t_{\text{flight}}}=\frac{2\,{v_{\text{launch}}}\,\sin\left(θ\right)}{g}
	$$
2. By [[Calculating of landing position (InstanceModel)]], we define [[landing position (ConstrConcept)]] as:
	$$
	{p_{\text{land}}}=\frac{2\,{v_{\text{launch}}}^{2}\,\sin\left(θ\right)\,\cos\left(θ\right)}{g}
	$$
3. By [[Offset (InstanceModel)]], we define [[offset (ConstrConcept)]] as:
   $$
   {d_{\text{offset}}}={p_{\text{land}}}-{p_{\text{target}}}
   $$

4. By [[Output message (InstanceModel)]], we define [[message (QuantityDict)]] as:
   $$
   s=\begin{cases}
                            \text{``The target was hit.''}, & |\frac{{d_{\text{offset}}}}{{p_{\text{target}}}}|\lt{}ε\\
                            \text{``The projectile fell short.''}, & {d_{\text{offset}}}\lt{}0\\
                            \text{``The projectile went long.''}, & {d_{\text{offset}}}\gt{}0
                            \end{cases}
   $$

This corresponds with the order of operations the generated Python code follows (taking [projectile_m_p_nol_b_u_v_d](https://github.com/JacquesCarette/Drasil/blob/5705da6c270bd1839801037c71a5e8466072e655/code/stable/projectile/projectile_m_p_nol_b_u_v_d/src/python/Control.py#L15-L20), for example):
```python
inParams = InputParameters.InputParameters(filename)
t_flight = Calculations.func_t_flight(inParams, g)
p_land = Calculations.func_p_land(inParams, g)
d_offset = Calculations.func_d_offset(inParams, p_land)
s = Calculations.func_s(inParams, epsilon, d_offset)
OutputFormat.write_output(s, d_offset, t_flight)
```

### Remaining SI Components

There are three other components to the SI that are irrelevant to the "essence" of "Projectile:"

```haskell
  _sysinfodb   = symbMap,
  _usedinfodb. = usedDB,
  _configFiles = []
```
#### Two ChunkDBs

* `sysinfodb`/`symbMap`: We brand each of our chunks with [[UID]]s. We expect that each time a chunk needs to refer to another, it stores the other's [[UID]] rather than a copy of the other entirely. This gives us the ability to see the dependency tree of our [[Chunk|chunk]]s. This is an operational issue of how we're using Haskell to:
	* Encode our chunk types.
	* Build instances of our chunk types.
	* Interpret our chunk instances for software generation.
  I will not explain all of our chunks from the [[ChunkDB]] here. The only ones referenced are the ones immediately relevant to the [[Projectile System]].
* `usedinfodb`/`usedDB`: [This is a wart](https://github.com/JacquesCarette/Drasil/issues/1661#issuecomment-1021450950). It is marked for removal once we can handle the operational issues properly.
#### Config Files

`configFiles` is only used for GlassBR. It contains a list of files necessary for the software problem to run.
