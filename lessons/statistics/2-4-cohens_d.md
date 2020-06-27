[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Exercise 1   Based on the results in this chapter, suppose you were asked to summarize what you learned about whether first babies arrive late.
Which summary statistics would you use if you wanted to get a story on the evening news? Which ones would you use if you wanted to reassure an anxious patient?

Finally, imagine that you are Cecil Adams, author of The Straight Dope (http://straightdope.com), and your job is to answer the question, “Do first babies arrive late?” Write a paragraph that uses the results in this chapter to answer the question clearly, precisely, and honestly.

Answer: I would use mean value if I wanted to get a story on the evening news. I would use mode if I wanted to reassure an anxious patient.

According to the mean length of the pregnancy, the first babies arrive later than the other babies. However, the difference is insignificant. 

Exercise 2   In the repository you downloaded, you should find a file named chap02ex.ipynb; open it. Some cells are already filled in, and you should execute them. Other cells give you instructions for exercises. Follow the instructions and fill in the answers.
A solution to this exercise is in chap02soln.ipynb

In the repository you downloaded, you should find a file named chap02ex.py; you can use this file as a starting place for the following exercises. My solution is in chap02soln.py.

Exercise 3   The mode of a distribution is the most frequent value; see http://wikipedia.org/wiki/Mode_(statistics). Write a function called Mode that takes a Hist and returns the most frequent value.
As a more challenging exercise, write a function called AllModes that returns a list of value-frequency pairs in descending order of frequency.

def Mode(Hist):
    freq0=0
    val0=0
    for val, freq in Hist.Items():
        if freq>freq0:
            val0=val
            freq0=freq
    return val0
    
def AllModes(hist):
    list_hist=[]
    for val,freq in hist.Items():
        list_hist.append((val,freq))
    list_hist=sorted(list_hist, key=lambda x: x[1], reverse=True)
    return list_hist
    
Exercise 4   Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s d to quantify the difference between the groups. How does it compare to the difference in pregnancy length?
    
firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
#the output is -0.12476118453549034, which indicates the first babies are lighter than others.
CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
#the output is -0.088672927072602


