---
title: Haskell in Leipzipg
subtitle: Detailed Program
---

Invited talk
------------

### Preserving Privacy with Monads ## {#russo}

*by [Alejandro Russo](http://www.cse.chalmers.se/~russo/)*

In a all-connected society, users consciously (or unconsciously) value their
privacy. Even skeptical people will recognize its importance; if they do not,
ask them to unlock their smartphone and hand it out to someone else---they will
most probably refuse!  Users want to have control on how their data gets
disseminated, specially today when private information gets handled by software
with heterogeneous trustworthiness---consider, for example, the various
smartphones apps with access to users' private photos, messages, and contacts
that exists today.  Unfortunately, current software practices are insufficient
to protect privacy: users who wish to benefit from software functionality are
often forced to grant access to their private data with no guarantees how it
gets handled. The key insight to guarantee privacy is not about granting or
denying access to private data, but ensuring that information only flows into
the appropriated places.

Information-Flow Control (IFC) is a research area dedicated to protect privacy
of data. Based on programming languages techniques, IFC scrutinizes source code
to track how data of different sensitivity levels (e.g., public or private)
flows within a program, where alarms are raised when privacy might be at stake.
IFC tools often provide specially designed compilers to build privacy-preserving
apps. Rather than building a compiler from scratch (a major task on its own),
Haskell plays a unique privileged role in this scenario: it can provide IFC
security via libraries. As long as developers program against the libraries'
API, code is secure by construction. This talk shows how to build such libraries
by specially designing monads capable to restrict the propagation of private
data. The presentation explores the different techniques used in a wide range of
libraries, namely LIO, MAC, and HLIO, where IFC is enforced dynamically (in the
form of an execution monitor), statically (by leveraging Haskell's type-system),
and as a combination of both.


**Short bio**: [Alejandro Russo] is an associate professor at Chalmers
University of Technology working on the intersection of functional languages,
security, and systems. He is the recipient of a Google Research Awards and
several grants from the Swedish research agencies Vetenskapsrådet, STINT, and
Barbro Osher foundation. Internationally, Prof. Russo worked on prestigious
research institutions like Stanford University, where he was appointed visiting
associate professor. His research ranges from foundational aspects of security
to developing tools to secure software written in Haskell, Python, and
JavaScript.

[Alejandro Russo](http://www.cse.chalmers.se/~russo/)

## Contributed Talks

### Automated Performance Measurements {#waldmann}

*by [Johannes Waldmann]*

### Generalized Algebraic Dynamic Programming: Theory and Applications in Bioinformatics and Linguistics {#stadler}
*by Sarah J. Berkemer, [Peter F. Stadler] and [Christian Hoener Zu Siederdissen]:*

### HGamer3D - a toolset for developing games with Haskell {#althainz}
*by Peter Althainz*

### Management at Algorithmic Financial Markets {#winschel}
*by Viktor Winschel*

### Project report: building a web-application with servant, lucid, and digestive-functors {#fischmann}
*by Matthias Fischmann and Andor Penzes:*

### Dependently Typed Heaps {#brunjes}
*by [Lars Brünjes]*


### Random access lists, nested data types and numeral systems {#komuves}
*by Balazs Komuves*

### Plugin Architectures in Haskell {#graf}
*by Sebastian Graf*

### Store: An Efficient Binary Serialization Library {#kant}
*by Philipp Kant*

### Csound-expression Haskell framework for computer music {#kholomiov-talk}
*by Anton Kholomiov*

(Note the corresponding [tutorial](#kholomiov-tutorial).)

### Simple blog engine with shape functors and generic eliminators for ADTs {#penez}
*by Andor Penzes*

## Tutorials

### Efficient signal processing using Haskell and LLVM {#thielemann}
*by [Henning Thielemann]*

Haskell has so many features that are useful for signal processing:
Lazy evaluation allows for infinite lists,
simultaneous processing of a sequence of signal transformations and feedback,
monads allow for proper handling of coherent and incoherent sources of noise,
the type system allows for handling of sample rates via phantom types
and for hiding internal filter parameters in opaque types.
However, especially when relying on a lot of laziness
your Haskell programs will be pretty slow in any Haskell implementation.
In order to get reasonable processing speed
you need to switch from lazy lists of sampled displacements
to lazy lists of chunks of unboxed arrays.
This compromise is pretty close to how signals are usually stored
in signal processing packages written in machine oriented languages.
However, GHC still fails to generate efficient code
in cases that are hard to predict.
It may be due to missing inlining, too much sharing of functions
or too much laziness.

With the package `synthesizer-llvm`
we address the issue of efficient signal processing.
We use the LLVM Just-In-Time compiler
in order to perform signal processing with maximum speed.
LLVM provides optimization passes and vector instructions
that enable us to achieve this goal.
Our package also provides the programmer
precise control over strict evaluation,
code and data duplication or sharing.

In the tutorial we examine the examples included in the package,
experiment with them and learn about the basic concepts of the package this way.
The examples include:

 * Signal producers like oscillators and noise generator,
 * Frequency filters and how to work with internal filter parameters
   beyond the restricting scheme of audio and control rates
   found in other digital signal processing frameworks,
 * Sample value types: Stereo sounds, binary logic signals, fixed-size arrays
 * Causal signal processes with arrows,
   sharing and feedback with proven absence of deadlocks,
 * Express arrows by plain functions,
 * Composing sequences of sounds, composing music from tones,
 * MIDI control of sounds,
 * Integration with ALSA and JACK,
 * Vectorisation.

I already gave a tutorial on LLVM at [HaL-9](https://iba-cg.de/hal9.html)
and chose simple signal processing as application.
In this tutorial I will ignore the details of LLVM
and just concentrate on the signal processing part.
I do not plan to give an extensive introduction to signal processing,
the focus is on how to get things done with `synthesizer-llvm`.

Since LLVM changes slightly with every release
my LLVM bindings got a bit out of date.
I am currently updating them.
The tricky part to install is the package `llvm-ffi`.
If you want to attend the tutorial and want to code with us,
please send me your e-mail.
I will then notify you when my packages are ready for installation
and I will give you hints on the installation.


References:

 * [synthesizer-llvm](http://hackage.haskell.org/package/synthesizer-llvm)
   package at Hackage
 * Paper "Compiling Signal Processing Code embedded in Haskell via LLVM"
   at [arXiv](http://arxiv.org/abs/1004.4796)
 * [Demo of a song](https://www.youtube.com/watch?v=4zX0OnLGVV4)
   that is played live over a synthesizer-llvm based software synthesizer.


### Workshop: creating computer music with Haskell {#kholomiov-tutorial}
*by [Anton Kholomiov]*

(Note the corresponding [talk](#kholomiov-talk).)

### Ten example uses of monads {#schuster}
*by [Philipp Schuster]*

This is a workshop for Haskell beginners that motivates monads. In this “monad tutorial” we are not going to learn what monads are, how they are implemented or how they work internally. After a quick introduction to the syntax we are going to look at ten practical use cases. We will look at a selection of concurrency, resource management, build dependencies, stream processing, distributed programming, probabilities, server programming, database queries, mutable references, search, test specification and parsing.

I provide a [repository on github](https://github.com/phischu/monad-examples) with a small example for each monad discussed. If you want to follow along you should clone that repository and start from there. To compile the examples you can use either [cabal](https://www.haskell.org/cabal/) or [stack](http://docs.haskellstack.org/en/stable/README/). We will go through each example to motivate the used monad. Then we will extend each example with a small feature.

We will keep selecting examples from the following list until the time is up.

 * [STM](https://hackage.haskell.org/package/stm-2.4.4.1/docs/Control-Monad-STM.html#t:STM): Software transactional memory for concurrency.
 * [Resource](https://hackage.haskell.org/package/resourcet-1.1.7.4/docs/Control-Monad-Trans-Resource.html#t:ResourceT): Automatic resource management.
 * [Action (shake)](https://hackage.haskell.org/package/shake/docs/Development-Shake.html#t:Action): GNU make embedded in Haskell.
 * [Pipe](https://hackage.haskell.org/package/pipes-4.2.0/docs/Pipes.html#t:Pipe): Stream processing.
 * [Process](https://hackage.haskell.org/package/distributed-process-0.6.1/docs/Control-Distributed-Process.html#t:Process): Distributed programming.
 * [Probability](https://hackage.haskell.org/package/probability-0.2.5/docs/Numeric-Probability-Distribution.html#t:T): Probability distributions.
 * [Scotty](https://hackage.haskell.org/package/scotty-0.10.2/docs/Web-Scotty.html#t:ScottyM): Web server framework.
 * [Relation](https://hackage.haskell.org/package/relational-query-0.8.2.1/docs/Database-Relational-Query-Monad-BaseType.html#t:Relation): SQL embedded in Haskell.
 * [ST](https://hackage.haskell.org/package/base-4.9.0.0/docs/Control-Monad-ST.html#t:ST): Mutable references.
 * [Logic](https://hackage.haskell.org/package/logict-0.6.0.2/docs/Control-Monad-Logic.html#t:Logic): Backtracking search.
 * [Spec](https://hackage.haskell.org/package/hspec-core-2.2.3/docs/Test-Hspec-Core-Spec.html#t:Spec): Test specification.
 * [Parser](https://hackage.haskell.org/package/attoparsec-0.13.0.2/docs/Data-Attoparsec-ByteString.html#t:Parser): Parse binary and textual data.
 * [Canvas](https://hackage.haskell.org/package/blank-canvas-0.6/docs/Graphics-Blank.html#t:Canvas): Draw on HTML 5 Canvas.

Those examples hopefully demonstrate the broad applicability of the monad concept.


[Johannes Waldmann]: http://www.imn.htwk-leipzig.de/~waldmann/
[Peter F. Stadler]: http://www.bioinf.uni-leipzig.de/
[Christian Hoener Zu Siederdissen]: http://www.bioinf.uni-leipzig.de/~choener/index.html
[Lars Brünjes]:  https://github.com/brunjlar
[Anton Kholomiov]: https://github.com/anton-k
[Henning Thielemann]: http://dr.henning-thielemann.de/
[Philipp Schuster]: https://github.com/phischu/

