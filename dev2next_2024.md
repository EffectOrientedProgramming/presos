## Effect Oriented Programming

#### James Ward
*Developer Advocate @ AWS* <a href="https://twitter.com/_JamesWard?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large">@_JamesWard</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

#### Bruce Eckel
*Author/Consultant* <a href="https://www.mindviewllc.com/">MindView LLC</a> <a href="https://twitter.com/BruceEckel" class="twitter-follow-button" data-size="large">@BruceEckel</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

#### Bill Frasure
*Developer*

---

<div style="display: flex; align-items: flex-start; justify-content: space-between; padding: 20px;">
    <img src="images/Restaurant.webp" style="max-width: 60%; height: auto; margin-right: 20px;">

<span style="font-size: 16px;">(From a Rory Sutherland TED talk)</span>
</div>


---

<div style="display: flex; align-items: flex-start; justify-content: space-between; padding: 20px;">
    <img src="images/Restaurant.webp" style="max-width: 60%; height: auto; margin-right: 20px;">

- Food Rating: 8.5/10
</div>

---

<div style="display: flex; align-items: flex-start; justify-content: space-between; padding: 20px;">
    <img src="images/Restaurant.webp" style="max-width: 60%; height: auto; margin-right: 20px;">

- Food Rating: 8.5/10
- Restaurant goal: 9/10
</div>


---

<div style="display: flex; align-items: flex-start; justify-content: space-between; padding: 50px; text-align: center;">
<img src="images/BillJamesBruce.png" style="width: 65%;">
What Problem are we Solving?
</div>

---

<div style="display: flex; align-items: flex-start; justify-content: space-between; padding: 50px; text-align: center;">
<img src="images/software-lego.webp" style="width: 65%;">
Building Blocks => Composability
</div>

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

<div style="text-align: center; font-size: 30px; position: absolute; top: 70%; left: 70%; transform: translate(-50%, -50%);">
Cool
</div>

---

<div style="position: absolute; bottom: 10%; right: 10%; font-size: 50px;">
Remind me why we would do this?
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
- The Surprises Make it Hard to Test & Compose

---

## Even the Simplest Functions can Produce Surprises 

<pre style="font-size: 50px; text-align: left;">
def divide(a: Int, b: Int): Int =
  a / b
</pre>

---

# Surprises == *Side Effects*

---

# *Effect Systems* Turn Side Effects into *Effects*

---

# *Effect<span class="spc">&nbsp;</span>Systems*<span class="spc">&nbsp;</span>Turn<span class="spc">&nbsp;</span>Side<span class="spc">&nbsp;</span>Effects<span class="spc">&nbsp;</span>into<span class="spc">&nbsp;</span>*Effects*


---

## Oversimplified to Show the Idea:
<pre style="font-size: 50px; text-align: left;">
def c(a: Int, b: Int): Int =
  a + b + <span style="background-color: orange;">ControlledRandom.nextInt()</span>
</pre>

---

# To Keep **This** From Happening To Me (Again)

<img src="images/NoSleep.png" style="width: 20%;">

- Bill & James abstracted away the underlying machinery—including much of Scala
- If you're a purist this might make you mad
- We're going to risk it
