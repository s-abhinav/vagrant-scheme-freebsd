**Vagrant Scheme FreeBSD** is a development environment configured specifically for writing Scheme code using the 
GNU Guile implementation of the Scheme programming language. Vagrant has been used to facilitate the deployment of the underlying
operating system on Windows. 

The environment features
- [Emacs](https://www.gnu.org/software/emacs/)
- [Geiser](http://www.nongnu.org/geiser/)
- [ParEdit](https://www.emacswiki.org/emacs/ParEdit)

The combination of these features make the development of Scheme code easy.

### Setup
The development environment requires [Vagrant](https://www.vagrantup.com/) and a virtual machine provider such as 
[VirtualBox](https://www.virtualbox.org/). 
To install
1. `git clone` this respository and `cd` into it. 
2. run `vagrant up`.
3. `vagrant ssh` to log into the development environment.

### Development
To run your first Scheme code, 
1. run `emacs test.scm`.
2. Type in 
```Scheme
(define (square x)
  (* x x))

(square 3)
```
3. Type `M-x` followed by `run-geiser` where M is the meta key.
4. Typing the return key at this point will open the Guile REPL in another buffer. Since the cursor has switched to the new buffer,
you would need to bring it back to the test.scm buffer. To do this, type `C-x o` where C is the Control key.
5. The test.scm buffer is ready to be evaluated. To run the code, type [`C-c C-b`](http://www.nongnu.org/geiser/geiser_5.html).
The result will be displayed in the [minibuffer](https://www.emacswiki.org/emacs/MiniBuffer#minibuffer).

### Note 

- FreeBSD has been chosen with no specific reason except to provide Guile with a fully supported environment
to run properly. Guile in Cygwin does not work well.
- I mentioned that it would be easy with this setup if you know Emacs, otherwise it's not easier than a simple text editor
or DrRacket. The learning curve with a simple text editor is almost non existent, so that makes you think, why should I choose
something that I can use right away over another setup that takes forever to learn and is overly complex. The fact that you 
even asked this question means that you must be missing a lot with simple text editors. How much is a lot? The answer is complex. Maybe
 you can have an idea by answering these questions instead. How much time are you wasting by 
  - switching your fingers from the keyboard to the mouse?
  - visually finding the run / execute button, pointing the cursor and clicking to evaluate the code. This is one of the operations
 that you do the most while developing. Even if you do use the keyboard for this, you don't have fine controls over what exactly
 gets evaluated. Is it the whole buffer, the current procedure, the current line or a symbol?
  - using the cursor keys? Now you will be like, seriously, cursor keys?
  - having to repeatedly switch to the REPL to evaluate a small piece of code?

  There is an endless list of time wasting scenarios. It's actually not time wasting, if you don't know the difference it takes
to "run" the code in a simple text editor as compared to running precisely what you need instantaneously in this setup. How about
having to lookup the value of a definition? You get that for free by pointing the cursor to it. The Geiser integration with Scheme 
evaluates it in the minibuffer right away. You don't know what you are missing, unless you study what's possible with this setup. 
The first thing to start with is learning Emacs. The investment will definitely pay off. The second on the list, is 
[learning Geiser](http://www.nongnu.org/geiser/geiser_5.html#Cheat-sheet). Finally, [ParEdit](http://emacsrocks.com/e14.html)
will be the cherry on top.
