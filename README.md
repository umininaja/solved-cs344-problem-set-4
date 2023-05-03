Download Link: https://assignmentchef.com/product/solved-cs344-problem-set-4
<br>
<strong>Drawing graphs: </strong>You might try http://madebyevan.com/fsm/ which allows you to draw graphs with your mouse and convert it into L<sup>A</sup>TEXcode:

You can also draw by hand and insert a picture.

<strong>Make best use of picture in Latex</strong>: If you think some part of your answer is too difficult to type using Latex, you may write that part on paper and scan it as a picture, and then insert that part into Latex as a picture, and finally Latex will compile the picture into the final PDF output. This will make things easier. For instructions of how to insert pictures in Latex, you may refer to the Latex file of our homework 1, which includes several examples of inserting pictures in Latex.

Discussion Group (People with whom you discussed ideas used in your answers if any):

I acknowledge and accept the Honor Code. Please type your initials below: <strong>Signed</strong>: (YC)

<ol>

 <li><strong>Longest Common Subsequence </strong>(20 points)</li>

</ol>

Consider the two sequences penguin and chicken, using the LCS algorithm we learnt in class, find the longest common subsequence of these two words.

<ul>

 <li>(10 points) Work out the 2-dimensional dynamic programming table <em>T</em>(<em>i,j</em>) and provide the length of the LCS.</li>

</ul>

<strong>[You are expected to work out every element of the dynamic programming</strong>

<strong>table.]</strong>

Figure 1: Question 1(a).

Answer: The length of the LCS is 2.

<ul>

 <li>(10 points) Traceback on the table to find out the exact longest common subsequence(s) of the two words.</li>

</ul>

<strong>[You are required to draw the traceback path(s) on the table and find out all the LCSs.]</strong>

Answer: There are two paths. The longest common subsequence of blue path is <em>in</em>. The longest common subsequence of pink path is <em>en</em>.

Figure 2: Question 1(b).

<ol start="2">

 <li><strong>Longest Increasing Subsequence </strong>(20 points + 5 bonus points)</li>

</ol>

Let <em>A </em>be an array of length <em>n </em>containing real numbers. A <em>longest increasing subsequence </em>(LIS) of <em>A </em>is a sequence 0 ≤ <em>i</em><sub>1 </sub><em>&lt; i</em><sub>2 </sub><em>&lt; …i<sub>` </sub>&lt; n </em>so that <em>A</em>[<em>i</em><sub>1</sub>] <em>&lt; A</em>[<em>i</em><sub>2</sub>] <em>&lt; </em>··· <em>&lt; A</em>[<em>i<sub>`</sub></em>], so that <em>` </em>is as long as possible. For example, if <em>A </em>= [6<em>,</em>3<em>,</em>2<em>,</em>5<em>,</em>6<em>,</em>4<em>,</em>8], then an LIS is <em>i</em><sub>0 </sub>= 2<em>,i</em><sub>1 </sub>= 3<em>,i</em><sub>2 </sub>= 4<em>,i</em><sub>3 </sub>= 6 corresponding to the subsequence 2<em>,</em>5<em>,</em>6<em>,</em>8. (Notice that a longest increasing subsequence does not need to be unique). In the following parts, we will walk through the recipe that we saw in class for coming up with DP algorithms to develop an <em>O</em>(<em>n</em><sup>2</sup>)-time algorithm for finding an LIS.

<ul>

 <li>(10 points) <strong>(Identify optimal sub-structure and a recursive relationship). </strong>We will come up with the sub-problems and recursive relationship for you, although you will have to justify it. Let <em>D</em>[<em>i</em>] be the length of the longest increasing subsequence of [<em>A</em>[0]<em>,…,A</em>[<em>i</em>]] that ends on <em>A</em>[<em>i</em>]. Expain why</li>

</ul>

<em>D</em>[<em>i</em>] = max{<em>D</em>[<em>k</em>] + 1 : 0 ≤ <em>k &lt; i,A</em>[<em>k</em>] <em>&lt; A</em>[<em>i</em>]}<em>.</em>

<em>k</em>

[<strong>Provide a short informal explanation. It is good practice to write a formal proof, but this is not required for credit.</strong>]

Answer:Given<em>D</em>[<em>i</em>] is the length of the longest increasing subsequence of [<em>A</em>[0]<em>,…,A</em>[<em>i</em>]] that ends on <em>A</em>[<em>i</em>].We can express that the length of the longest increasing subsequence ending at any index ”i” will be 1 more than max, that is, all the lengths of the longest increasing subsequence ending before the ith index, and where, for all k ¡ i, A [k] ¡A [i]. We divide this array into many sub-array.first, we can ignore A[i], and see the first i-1elenments, then we find LIS of first (i-1) elenments. final, we add 1 into the D[i].

Figure 3: Question 2(a).

Therefore, the max of k is 3, then 3+1 = 4, the length of LIS of A[i] is 4.

(b) (10 points) <strong>(Develop a DP algorithm to find the value of the optimal solution) </strong>Use the relationship above to design a dynamic programming algorithm that returns the <em>length </em>of the longest increasing subsequence. Your algorithm should run in time <em>O</em>(<em>n</em><sup>2</sup>) and should fill in the array <em>D </em>defined above.

[<strong>Provide the pseudo-code, and a brief justification of why the complexity is </strong><em>O</em>(<em>n</em><sup>2</sup>)<strong>, no formal proof is required.</strong>] Answer: function getLIS(int[] A, int n) initial variable array <em>&gt; </em>int D[size n] set <em>D</em>[0] <em>&lt; </em>−1 FOR (<em>i </em>= 1<em>,i &lt;</em>= <em>n,i </em>+ +) set <em>D</em>[<em>i</em>] <em>&lt; </em>−1

FOR (<em>k </em>= 0<em>,k &lt;</em>= <em>i,k </em>+ +)

IF (<em>A</em>[<em>i</em>] <em>&gt;</em>= <em>A</em>[<em>k</em>] and <em>D</em>[<em>i</em>] <em>&lt;</em>= <em>D</em>[<em>k</em>] + 1) set <em>D</em>[<em>i</em>] <em>&lt; </em>−<em>D</em>[<em>k</em>] + 1

END IF

END FOR

END FOR

initial variable lengthLIS <em>&lt; </em>−1

FOR(<em>i </em>= 1<em>,i &lt;</em>= <em>n,i </em>+ +) IF (<em>D</em>[<em>i</em>] <em>&gt;</em>= <em>lengthLIS</em>) set <em>lengthLIS &lt; </em>−<em>D</em>[<em>i</em>]

END IF

END FOR

return lengthLIS

For this algorithm, we have to consider the outer loop and inner loop. The inner loop k moves from 0 to i, there are n times for each iteration of the outer loop, so for each iteration of the outer loop, we must move at most n previous elements and in the inner for loop. Therefore, the complexity is <em>O</em>(<em>n</em><sup>2</sup>).

(c) (5 bonus points) <strong>(Adapt the DP algorithm to return the optimal solution) </strong>Adapt your algorithm above by tracking some useful information during the DP procedure, so that it returns the actual LIS, not just its length.

[<strong>Pseudocode and a short explanation.</strong>]

<strong>Note: </strong>Actually, there is an <em>O</em>(<em>n</em>log<em>n</em>)-time algorithm to find an LIS, which is faster than the DP solution in this exercise.

Answer:

Input: An array A

Output: The Longest Increasing Sub-sequence of A Function longestIncreasingSubsequence(A)

<em>a </em>= 0

FOR (<em>i </em>= 1<em>ton </em>− 1):

IF (<em>A</em>[<em>i</em>] <em>&gt; A</em>[<em>I</em>[<em>a</em>]])

<em>a </em>= <em>a </em>+ 1

<em>I</em>[<em>a</em>] = <em>i</em>

<em>P</em>[<em>a </em>− 1] = <em>I</em>[<em>a </em>− 1]

ENDIF ELSE

do binary search in <em>I</em>[1<em>…a</em>] for j such that: <em>A</em>[<em>I</em>[<em>j</em>]] is the smallest element in all

<em>A</em>[<em>I</em>[<em>j</em>]],

<em>j </em>= 0<em>,</em>1<em>,…length</em>(<em>I</em>[ ])<em>andA</em>[<em>I</em>[<em>j</em>]] <em>&gt; A</em>[<em>i</em>]

<em>I</em>[<em>j</em>] = <em>i</em>

END ELSE if <em>j </em>== <em>a P</em>[<em>b</em>] = <em>I</em>[<em>a </em>− 1]

ENDIF

ENDELSE

ENDFOR

<em>LIS</em>[<em>a</em>] = <em>A</em>[<em>I</em>[<em>a</em>]]

FOR (<em>i </em>= <em>a </em>− 1<em>,i &lt;</em>= 1<em>,i </em>− −)

<em>LIS</em>[<em>i</em>] = <em>A</em>[<em>P</em>[<em>b</em>]]

ENDFOR

return LIS

when the new element is not larger, we find the smallest element in the LIS sequence that is larger than our value and replace it with our current value. We could use binary search to find this element since the index of the value by I[ ] are in ascending order. This runs in O(log(n)) time.