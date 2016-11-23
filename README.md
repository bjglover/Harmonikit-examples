### Harmonikit examples

Work in progress to create new patches and documentation for Harmonikit


### Introduction

Harmonikit is an additive synthesiser created by Rich Hickey, and the subject of his talk at Clojure/conj 2013.

https://www.youtube.com/watch?v=bhkdyCPYgLs

It was designed to work with "Overtone", a Clojure-based platform for synthesis and music


### Requirements

I set this up on Windows 7 64bit, though the requirements for other platforms are probably the same.

1) Leiningen will get you up and running with Clojure
http://leiningen.org/

2) SuperCollider, the underlying synth engine. (I used the standalone version. See Resources folder for sample startup file.)
http://supercollider.github.io/

3) Overtone
http://overtone.github.io/

4) Emacs was used for testing and compilation, configured as described here
http://www.braveclojure.com/basic-emacs/

5) An iPad with the Lemur app is needed as a controller. (See Resources folder for template. For some reason I found I needed to copy and paste the contents of the JZML file into a new text document instead of saving it straight out from Github, but maybe I just did it wrong. It can then be copied to the Lemur app folder on the iPad using iTunes. You'll need to install the Lemur software on the computer and configure the app with the computer's IP address on port 4242, which is the one referenced in harmonikit.clj)
https://liine.net/en/products/lemur/

