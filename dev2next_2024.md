## Effect Oriented Programming

#### James Ward
*Developer Advocate @ AWS* <a href="https://twitter.com/_JamesWard?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large">@_JamesWard</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

#### Bruce Eckel
*Author/Consultant* <a href="https://www.mindviewllc.com/">MindView LLC</a>

#### Bill Frasure
*Developer*

---

<img src="images/BillJamesBruce.png" style="width: 65%;">


---

<img src="images/software-lego.webp" style="width: 65%;">

---

<pre style="font-size: 150px; text-align: center;">
f(g(h()))
</pre>

---

<p style="font-size: 65px; text-align: center;">
A sentence is composed of words.
</p>

---

<style>
  .spc {
    background-color: orange;
    display: inline-block;
    height: 35px;
    vertical-align: middle;
  }
</style>

<p style="font-size: 65px; text-align: center;">
  A<span class="spc">&nbsp;</span>sentence<span class="spc">&nbsp;</span>is<span class="spc">&nbsp;</span>composed<span class="spc">&nbsp;</span>of<span class="spc">&nbsp;</span>words.
</p>

---

<pre style="font-size: 150px; text-align: center;">
f(g(h()))
</pre>

---

<style>
  .spc2 {
    background-color: orange;
    display: inline-block;
    height: 100px;
    vertical-align: middle;
  }
</style>

<pre style="font-size: 150px; text-align: center;">
<span class="spc2">&nbsp;</span>f(<span class="spc2">&nbsp;</span>g(<span class="spc2">&nbsp;</span>h()))
</pre>

---

<div style="position: absolute; top: 10%; left: 10%; font-size: 180px;">
Cool
</div>

---

<div style="text-align: center; font-size: 60px; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);">
Cool
</div>

---

<div style="position: absolute; bottom: 10%; right: 10%; font-size: 50px;">
What problem are we solving, again?
</div>

---

# What Impedes Composability?

---

<pre style="font-size: 50px; text-align: left;">
def p(a: Int, b: Int): Int =
  a + b
</pre>

- No Surprises
- Results can be cached
- *Pure* function
- Because there are no Surprises: Easily Composed

---

<pre style="font-size: 50px; text-align: left;">
def u(a: Int, b: Int): Int =
  a + b + scala.util.Random.nextInt()
</pre>

- Unpredictable, No Longer Pure
- The Surprises Make it Hard to Compose

---

## The Simplest Functions can Produce Surprises 

<pre style="font-size: 50px; text-align: left;">
def divide(a: Int, b: Int): Int =
  a / b
</pre>

---

# Side Effects

---

# *Effect Systems* Turn Side Effects into *Effects*

---

<pre style="font-size: 50px; text-align: left;">
def c(a: Int, b: Int): Int =
  a + b + <span style="background-color: orange;">ControlledRandom.nextInt()</span>
</pre>

---

# To Keep This From Happening To Me (Again)

<img src="images/NoSleep.png" style="width: 20%;">

- Bill & James abstracted away the underlying machinery
- If you're a purist this might make you mad
- We're going to risk it
