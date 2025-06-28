# Hunting for Memory Corruption on the Web 

WebAssembly enables fast execution of performance-critical in web applications
utilizing native code. However, recent research has demonstrated the potential
for memory corruption errors within WebAssembly modules to exploit web
applications. In this work, we present the first systematic analysis of memory
corruption in WebAssembly, unveiling the prevalence of a novel threat model
where memory corruption enables code injection on a victim’s browser. Our
large-scale analysis across 37797 domains reveals that an alarming 29411
(77.81\%) of those fully trust data coming from potentially attacker-controlled
sources. As a result, an attacker can exploit memory errors to manipulate the
WebAssembly memory, where the data is implicitly trusted and frequently passed
into security-sensitive functions such as eval or directly into the DOM via
innerHTML. Thus, an attacker can abuse this trust to gain JavaScript code
execution, i.e., Cross-Site Scripting (XSS).

To tackle this issue, we present Wemby, the first viable approach to
efficiently analyze WebAssembly-powered websites holistically. We demonstrate
that Wemby is proficient at detecting remotely exposed memory corruption errors
in web applications through fuzzing. For this purpose, we implement binary-only
WebAssembly instrumentation that provides fine-grained memory corruption
oracles. We applied Wemby to different websites, uncovering several memory
corruption bugs, including one on the Zoom platform. In terms of performance,
our ablation study demonstrates that Wemby outperforms current WebAssembly
fuzzers. Specifically, Wemby achieves an average speed improvement of 232 times
and delivers 46\% greater code coverage compared to the state-of-the-art.

```bibtex
@ARTICLE{Draissi2025-vc,
  title        = {Wemby’s web: Hunting for Memory Corruption in {WebAssembly}},
  author       = {Draissi, Oussama and Cloosters, Tobias and Klein, David and
                  Rodler, Michael and Musch, Marius and Johns, Martin and Davi,
                  Lucas},
  journaltitle = {Proceedings of the ACM on Software Engineering},
  publisher    = {Association for Computing Machinery (ACM)},
  date         = {2025-06-22},
  articleno    = {ISSTA059},
  doi          = {10.1145/3728937},
  url          = {https://dl.acm.org/doi/10.1145/3728937},
}
```
