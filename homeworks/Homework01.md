# Homework 1

# Google Colab and Python
* Watch how to use [Google Colab](https://www.youtube.com/watch?v=PVsS9WtwVB8)
* Practice Python3 - [notebook](../notebooks/python.ipynb) and watch [lecture](https://www.youtube.com/watch?v=V42qfAPybp8)
* If you are new to Python, I suggest practicing Python at online platforms such as [codewars.org](https://www.codewars.com/)
* If you fear learning new things (including Python), I also suggest that you watch [this](https://www.coursera.org/learn/learning-how-to-learn/home/welcome) world's most popular online course.

# Learn to plot functions
* Using free online tools such as [Desmos](https://www.desmos.com/calculator)

# Read sections 3.1 and 3.2 from CLRS
Please read this with the goal of using the knowledge to do the homework below.

# Watch the recorded lectures
- [Introduction](https://youtu.be/rP-sx1y4RS0)
- [Review insertion sort](https://www.youtube.com/watch?v=JU767SDMDvA)
- [Review merge sort](https://www.youtube.com/watch?v=4VqmGXwpLqc)
- [Analysis of insertion sort and merge sort](https://youtu.be/OT6CiGMhE90)
- [Asymptotic notations](https://youtu.be/53e9DxMK7EQ)

# Question 1
Reorder the following terms from lowest to highest time complexity, using `<` between terms. If two terms have the same complexity, use an equal sign instead. Assume `n>1` and `k` is a constant.
- O(n<sup>2</sup>)    
- O(kn)  
- O(1)  
- O(100000 * n)  
- O(n!)  
- O(lg n)
   - lg is log<sub>2</sub>  
- O(2n)  
- O(n)  
- O(k lg n)  
- O(n<sup>100000</sup>)  
- O(n * lg n)  

# Question 2 (CLRS 3.1-3)
- Explain why the statement, "The running time of algorithm A is at least O(n<sup>2</sup>)," is meaningless.

# Question 3 (CLRS 3.1-4)
- Is 2<sup>n+1</sup> = O(2<sup>n</sup>)? Explain.  
- Is 2<sup>2n</sup> = O(2<sup>n</sup>)? Explain.    

# Question 4 (From CLRS 3-3(a))
Rank the following functions by order of growth and **describe how you obtained the ranking**; i.e. find an arrangement g<sub>1</sub>, g<sub>2</sub>, ..., g<sub>N</sub> of the functions satisfying g<sub>1</sub> = Ω(g<sub>2</sub>), g<sub>2</sub> = Ω(g<sub>3</sub>), ..., g<sub>n-1</sub> = Ω(g<sub>N</sub>). Also discuss which of the functions are equivalent (by reducing whichever ones can be reduced).  Hint: Besides the mathematical analysis, two additional techniques that you MAY use to determine the growth are: (a) plotting the functions, and (b) timing the execution of the functions as shown [here](timing-execution.md).

<img src="ordering-growth-rate.png" align="center" width="350"/>


**Help:**   
- https://atekihcan.github.io/CLRS/P03-03/  
- https://atekihcan.github.io/CLRS/E03.01-04/  
