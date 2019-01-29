# Semantically Equivalent Adversarial Rules for Debugging NLP Models (Ribeiro et al.)

Complex models for RC and VQA are prone to brittleness; different ways of phrasing the same sentence often cause the model to output different predictions. This is called *oversensitivity*. In another way, adding a new word can have no semantic impact at all (known as *overstability*). 

<img src="https://github.com/anirbanl/anirbanl.github.io/blob/master/img/notes/sear-main.png" alt="drawing" width="400"/> 
It is possible to fool the model by adversarially changing a single character (c), but at the cost of making the question nonsensical. A **Semantically Equivalent Adversary** (d) results in an incorrect answer while preserving semantics.

## Main Contributions
1. Inspired by adversarial examples for images, they introduce semantically equivalent adversaries (SEAs) – text inputs that are perturbed in semantics-preserving ways, but induce changes in a black box model’s predictions. These are representative of real world scenarios compared to malicious attacks like misspellings, scrambling, removing words, etc.
2. Derivation of some semantics-preserving rules - semantically equivalent adversarial rules (SEARs), which are more globally applicable rather than perturbations to individual instances.
3. SEAs and SEARs, designed to unveil local and global oversensitivity bugs in NLP models.
4. Paraphrase generation techniques are used for to generate SEAs (model-agnostic). Next SEAs are generalized into semantically equivalent rules (SEARs). 

## Definition
Consider a black-box model <a href="https://www.codecogs.com/eqnedit.php?latex=$f$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$f$" title="$f$" /></a> that takes a sentence <a href="https://www.codecogs.com/eqnedit.php?latex=$x$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$x$" title="$x$" /></a> and produces <a href="https://www.codecogs.com/eqnedit.php?latex=$f(x)$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$f(x)$" title="$f(x)$" /></a>. A semantically equivalent adversary (SEA) is one that changes model prediction. SemEq(<a href="https://www.codecogs.com/eqnedit.php?latex=$x$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$x$" title="$x$" /></a>,<a href="https://www.codecogs.com/eqnedit.php?latex=$x^'$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$x^'$" title="$x^'$" /></a>) measures the semantic equivalence of its arguments (0 to 1). The following equation defines SEA:
<img src="https://github.com/anirbanl/anirbanl.github.io/blob/master/img/notes/sear-sea.png" alt="drawing" width="400"/>

### Example SEARs in different problem settings
<img src="https://github.com/anirbanl/anirbanl.github.io/blob/master/img/notes/sear-mc.png" alt="drawing" width="280"/> <img src="https://github.com/anirbanl/anirbanl.github.io/blob/master/img/notes/sear-vqa.png" alt="drawing" width="280"/> <img src="https://github.com/anirbanl/anirbanl.github.io/blob/master/img/notes/sear-sent.png" alt="drawing" width="280"/>
