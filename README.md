Download Link: https://assignmentchef.com/product/solved-machine-learning-hw2
<br>
<h1></h1>

<ol>

 <li><strong> Singletons </strong>(Section 3.5, Ex.2 in the course textbook). Let X be a discrete domain, and let H<em><sub>Singleton </sub></em>= {<em>h<sub>z </sub></em>: <em>z </em>∈ X} ∪ {<em>h</em><sup>−</sup>}, where for each <em>z </em>∈ X , <em>h<sub>z </sub></em>is the function defined by <em>h<sub>z</sub></em>(<em>x</em>) = 1 if <em>x </em>= <em>z </em>and <em>h<sub>z</sub></em>(<em>x</em>) = 0 if <em>x </em>6= <em>z</em>. <em>h</em><sup>− </sup>is simply the all-negative hypothesis, namely, ∀<em>x </em>∈ X<em>,h</em><sup>−</sup>(<em>x</em>) = 0.</li>

</ol>

The realizability assumption here implies that the true hypothesis <em>f </em>labels negatively all examples in the domain, perhaps except one.

Describe an algorithm that implements the ERM rule for learning H<em><sub>Singleton </sub></em>in the realizable setup.

<ol start="2">

 <li><strong>) PAC in Expectation</strong>. Consider learning in the realizable case. We say an hypothesis class H is <em>PAC learnable in expectation </em>if there exists a learning algorithm <em>A </em>and a function <em>N</em>(<em>a</em>) : (0<em>,</em>1) → N such that ∀<em>a </em>∈ (0<em>,</em>1) and for any distribution <em>P</em>, given a sample set <em>S</em>, such that |<em>S</em>| ≥ <em>N</em>(<em>a</em>) it holds that,</li>

</ol>

E[<em>e<sub>P</sub></em>(<em>A</em>(<em>S</em>))] ≤ <em>a</em>

Show that H is PAC learnable <em>if and only if </em>H is PAC learnable in expectation (Hint: Use Markov’s inequality and refer to derivations between equations 3.13-3.14 in the lecture scribes about VC).

<ol start="3">

 <li><strong> Union Of Intervals. </strong>Determine the VC-dimension of the subsets of the real line formed by the union of k intervals (see question 1 of the programming assignment for a formal definition of H).</li>

 <li><strong> Right-angle Triangles. </strong>Determine the VC-dimension of the hypotheses class H, of axis-aligned right-angle triangles in the plane, with the right angle in the lower left corner.</li>

 <li><strong>Structural Risk Minimization. </strong>Let H be a countable hypothesis class, that is, H can be written as H = <sup>S</sup><em><sub>i</sub></em><sub>∈</sub><sub>N</sub>{<em>h<sub>i</sub></em>}. Let <em>w </em>: H → [0<em>,</em>1] be a function such that <sup>P</sup><em>h</em>∈H <em>w</em>(<em>h</em>) ≤ 1. We refer to <em>w </em>as a <em>weight function </em>over the hypotheses which reflects the prior for each hypothesis.</li>

</ol>

(a) Show that with probability 1 − <em>δ </em>over the choice <em>S </em>∼ <em>P </em>(|<em>S</em>| = <em>n</em>)

1

2                                                                                         <em>Handout Homework 2: March 22, 2020</em>

Hint: use the uniform convergence property for each hypothesis class {<em>h<sub>i</sub></em>} of size

1.

(b) Denote. Show that with probability 1 − <em>δ</em>:

<em>,</em>

where <em>h<sub>min </sub></em>= <em>argmin e<sub>P</sub></em>(<em>h</em>).

<em>h</em>∈H

This implies that when the hypothesis with optimal error has high weight, it will be learned from few samples.

<ol start="6">

 <li><strong>(8 points) Loss Minimization. </strong>Consider binary classification with the following loss function:</li>

</ol>



0       <em>y </em>= <em>y</em>ˆ



∆<em><sub>b</sub></em>(<em>y,y</em>ˆ) =      0<em>.</em>5     <em>y </em>= 1<em>,y</em>ˆ = 0

1       <em>y </em>= 0<em>,y</em>ˆ = 1

Find the optimal classifier <em>h<sup>? </sup></em>= argmin<em><sub>h </sub></em>E[∆<em><sub>b</sub></em>(<em>Y,h</em>(<em>X</em>))].

<em>Handout Homework 2: March 22, 2020                                                                                          </em>3

<h1>Programming Assignment</h1>

<ol>

 <li><strong>Union Of Intervals. </strong>In this question, we will study the hypothesis class of a finite union of disjoint intervals, and the properties of the ERM algorithm for this class.</li>

</ol>

To review, let the sample space be X = [0<em>,</em>1] and assume we study a binary classification problem, i.e. Y = {0<em>,</em>1}. We will try to learn using an hypothesis class that consists of <em>k </em>intervals. More explicitly, let <em>I </em>= {[<em>l</em><sub>1</sub><em>,u</em><sub>1</sub>]<em>,…,</em>[<em>l<sub>k</sub>,u<sub>k</sub></em>]} be <em>k </em>disjoint intervals, such that 0 ≤ <em>l</em><sub>1 </sub>≤ <em>u</em><sub>1 </sub>≤ <em>l</em><sub>2 </sub>≤ <em>u</em><sub>2 </sub>≤ <em>… </em>≤ <em>u<sub>k </sub></em>≤ 1. For each such <em>k </em>disjoint

intervals, define the corresponding hypothesis as

(

1         if <em>x </em>∈ [<em>l</em><sub>1</sub><em>,u</em><sub>1</sub>]<em>,…,</em>[<em>l<sub>k</sub>,u<sub>k</sub></em>]

<em>h<sub>I</sub></em>(<em>x</em>) =

0     otherwise

Finally, define H<em><sub>k </sub></em>as the hypothesis class that consists of all hypotheses that correspond to <em>k </em>disjoint intervals:

H<em><sub>k </sub></em>= {<em>h<sub>I</sub></em>|<em>I </em>= {[<em>l</em><sub>1</sub><em>,u</em><sub>1</sub>]<em>,…,</em>[<em>l<sub>k</sub>,u<sub>k</sub></em>]}<em>, </em>0 ≤ <em>l</em><sub>1 </sub>≤ <em>u</em><sub>1 </sub>≤ <em>l</em><sub>2 </sub>≤ <em>u</em><sub>2 </sub>≤ <em>… </em>≤ <em>u<sub>k </sub></em>≤ 1}

We note that H<em><sub>k </sub></em>⊆ H<em><sub>k</sub></em><sub>+1</sub>, since we can always take one of the intervals to be of length 0 by setting its endpoints to be equal. We are given a sample of size <em>m </em>= h<em>x</em><sub>1</sub><em>,y</em><sub>1</sub>i<em>,…,</em>h<em>x<sub>n</sub>,y<sub>m</sub></em>i. Assume that the points are sorted, so that 0 ≤ <em>x</em><sub>1 </sub><em>&lt; x</em><sub>2 </sub><em>&lt; … &lt; x<sub>m </sub></em>≤ 1.

<u>Submission Guidelines:</u>

<ul>

 <li>Download the files py and intervals.py from Moodle. You should implement only the missing code in skeleton.py, as specified in the following questions. In every method description, you will find specific details on its input and return values.</li>

 <li>Your code should be written with python 3.</li>

 <li>Make sure to comment out / remove any code which halts the code execution, such as matplitlib popup.</li>

 <li>Your submission should include exactly two files: py, intervals.py.</li>

</ul>

Explanation on intervals.py:

The file intervals.py includes a function that implements an ERM algorithm for H<em><sub>k</sub></em>. Given a sorted list xs = [<em>x</em><sub>1</sub><em>,…,x<sub>m</sub></em>], the respective labeling ys = [<em>y</em><sub>1</sub><em>,…,y<sub>m</sub></em>] and <em>k</em>, the given function find best interval returns a list of up to <em>k </em>intervals and their error count on the given sample. These intervals have the smallest empirical error count possible from all choices of <em>k </em>intervals or less.

<em>Note that in sections (d)-(f) you will need to use this function for large values of m. Execution in these cases could take time (more than 10 minutes for experiment), so plan ahead.</em>

4                                                                                         <em>Handout Homework 2: March 22, 2020</em>

(a) <strong>(7 points) </strong>Assume that the true distribution <em>P</em>[<em>x,y</em>] = <em>P</em>[<em>y</em>|<em>x</em>] · <em>P</em>[<em>x</em>] is: <em>x </em>is distributed uniformly on the interval [0<em>,</em>1], and

(

0<em>.</em>8     if <em>x </em>∈ [0<em>,</em>0<em>.</em>2] ∪ [0<em>.</em>4<em>,</em>0<em>.</em>6] ∪ [0<em>.</em>8<em>,</em>1]

<em>P</em>[<em>y </em>= 1|<em>x</em>] =

0<em>.</em>1     if <em>x </em>∈ [0<em>.</em>2<em>,</em>0<em>.</em>4] ∪ [0<em>.</em>6<em>,</em>0<em>.</em>8]

and <em>P</em>[<em>y </em>= 0|<em>x</em>] = 1 − <em>P</em>[<em>y </em>= 1|<em>x</em>].

Write a function that draws <em>m </em>pairs of (<em>x,y</em>) according to the distribution <em>P</em>. Use it to draw a sample of size <em>m </em>= 100 and create a plot:

<ol>

 <li>Plot the points and their label (have the <em>y </em>axis in range −0<em>.</em>1<em>,</em>1<em>.</em>1 for clarity of presentation).</li>

 <li>Mark the lines <em>x </em>= 0<em>.</em>2<em>,</em>0<em>.</em>4<em>,</em>0<em>.</em>6<em>,</em>0<em>.</em>8 clearly on the plot.</li>

</ol>

<ul>

 <li>Run the find_best_interval function on your sample with <em>k </em>= 3, and plot the intervals clearly.</li>

</ul>

<ul>

 <li><strong>(7 points) </strong>Note that here, we know the true distribution <em>P</em>, so for every given hypothesis <em>h </em>∈ H<em><sub>k</sub></em>, we can calculate <em>error</em>(<em>h</em>) precisely. What is the hypothesis with the smallest error?</li>

 <li><strong>(7 points) </strong>Write a function that, given a list of intervals, calculates the error of the respective hypothesis. Then, for <em>k </em>= 3, <em>m </em>= 10<em>,</em>15<em>,</em>20<em>,…,</em>100, perform the following experiment <em>T </em>= 100 times: (i) Draw a sample of size <em>m </em>and run the ERM algorithm on it; (ii) Calculate the empirical error for the returned hypothesis; (iii) Calculate the true error for the returned hypothesis. Plot the average empirical and true errors, averaged across the <em>T </em>runs, as a function of <em>m</em>. Discuss the results. Do the empirical and true error decrease or increase in <em>m</em>? Why?</li>

 <li><strong>(7 points) </strong>Draw a data set of <em>m </em>= 1500 samples. Find the best ERM hypothesis for <em>k </em>= 1<em>,</em>2<em>,…,</em>20, and plot the empirical and true errors as a function of <em>k</em>. How does the error behave? Define <em>k</em><sup>∗ </sup>to be the <em>k </em>with the smallest empirical error for ERM? Does this mean the hypothesis with <em>k</em><sup>∗ </sup>intervals is a good choice?</li>

 <li><strong>(7 points) </strong>Now we will use the principle of structural risk minimization (SRM), to search for a <em>k </em>that gives good test error. Let <em>δ </em>= 0<em>.</em>1:

  <ul>

   <li>Use your results from question 3 in the theoretical part and the VC confidence bound to construct a penalty function.</li>

   <li>Draw a data set of <em>m </em>= 1500 samples, run the experiment in (d) again, but now plot two additional lines as a function of <em>k</em>: 1) the penalty for the best ERM hypothesis and 2) the sum of penalty and empirical error.</li>

   <li>What is the best value for <em>k </em>in each case? is it better than the one you chose in (d)?</li>

  </ul></li>

</ul>

(f) <strong>(7 points) </strong>Here we will use holdout-validation to search for a <em>k </em>that gives good test error. Draw a data set of <em>m </em>= 1500 samples and use 20% for a holdoutvalidation. Choose the best hypothesis based on 3 experiments. Discuss how close this gets you to finding the hypothesis with optimal true error.