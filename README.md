### Harmonikit examples

Work in progress to create new patches and documentation for Harmonikit



### Introduction

Harmonikit is an additive synthesiser created by Rich Hickey, and the subject of his talk at Clojure/conj 2013.

https://www.youtube.com/watch?v=bhkdyCPYgLs

It was designed to work with "Overtone", a Clojure-based platform for synthesis and music



### Requirements

I set this up on Windows 7 64bit, though the requirements for other platforms are probably the same.

1) Leiningen will get you up and running with Clojure:

http://leiningen.org/

Check you can open a REPL and run simple Clojure statements like: (+ 2 2)


2) SuperCollider, the underlying synth engine. (I used the standalone version. See Resources folder for sample startup file.)

http://supercollider.github.io/

Check you can run SuperCollider and launch the server. I used the following startup settings as the defaults didn't work for me.

    s = Server(\myServer, NetAddr("127.0.0.1", 58009));
    s.options.maxLogins = 5;
    s.options.memSize = 65536;
    s.options.device_("ASIO");
    s.boot; //start the server

3) Overtone:

http://overtone.github.io/

Check you can create an Overtone project, open a REPL, launch Overtone, connect to Supercollider with "connect-external-server" and make some sounds.


4) I used Emacs for testing and compilation, configured as described here:

http://www.braveclojure.com/basic-emacs/

Check you can use your REPL to start Overtone and connect to SuperCollider, then open the REPL in Emacs as described here:

https://github.com/overtone/overtone/wiki/Overtone-in-Emacs

Then check that you can open and compile the Harmonikit project, and make a noise by entering the following in the REPL:

    (harmonikit (buf/buffer-id b) 60)
    
If you hear a musical bleep, congratulations - Harmonikit is awake! 60 is the pitch. You can kill the sound with (srv/stop) before playing another.


5) An iPad with the Lemur app is needed as a controller. (See Resources folder for template. For some reason I found I needed to copy and paste the contents of the JZML file into a new text document instead of saving it straight out from Github, but maybe I just did it wrong. It can then be copied to the Lemur app folder on the iPad using iTunes.) 

https://liine.net/en/products/lemur/

You'll need to install the Lemur software on the computer and configure the app with the computer's IP address on port 4242, which is the one referenced in harmonikit.clj, in the following line:

    (def server (osc/osc-server 4242))

You'll also need to edit the following line to reflect the IP address of your iPad.

    (def client (osc/osc-client "iPad-IP-address-here" 8000))

Check that you can change the sound by selecting and deselcting harmonics in the interface. For debugging purposes, you might find it useful to direct the Lemur app at the SuperCollider server port; 58009 if you use the above startup settings. This will produce a stream of error messages in Supercollider if the computer is listening to Lemur. Remember to change it back the port 4242 again to control Harmonikit.
