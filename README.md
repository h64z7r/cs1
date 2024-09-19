java c
ECON 3720: Introduction to Econometrics
Problem Set 02
Fall Semester 2024
Due: September 20th  2024Please submit the problem set no later than 5 PM on September 20th  2024.  Submit the problem set to your TA’s mailbox in the Monroe Hall basement. Failure to do so will result in a a grade of 0. Remember to show all of your work.  Good luck!Additional note: Economic data sets available online are often in STATA’s  .dta or Microsoft Excel’s  .xlsx format  ( .xls for older data sets), both of which R will not be able to load by de- fault.  There are however external R packages  (available through  CRAN) which provide R with this functionality.  For  .dta files  (as well as various other file formats for other proprietary statistical analysis software packages), we have the haven package whereas for  .xlsx (or  .xls) files, we havethe readxl package.   The data sets on Canvas for questions 3 and 4 in this problem set are in .dta format. Make sure you download install the haven package before attempting either of these questions.
1)  Let Y1, Y2 , Y3 , Y4  be iid random variables from a population with mean µ and variance σ 2 .  Let Y =  + Y2 + Y3 + Y4) denote the (arithmetic) average of these four random variables.
a) What are the expected value and variance of Y in terms of µ and σ 2 ?
b)  Consider a different estimator of µ:

W = Y1 + Y2 + Y3 + Y4 .

This is an example of a weighted average of the Yi’s.  What are E[W] and Var[W]? Write your answers in terms of µ and σ .  Is W an unbiased estimator of µ?

c)  Based on your answers to parts a) and b), which estimator of µ do you prefer:  Y or W? [Note: This question is from the Wooldridge textbook (Problem C1 in the 7th  edition).]
2)  This question is long, but there hints along the way to help you out. All of this is doable using what we learned in probability review! In this question, we will derive the expected value of the two sample variance estimators introduced in lecture. Let  Var[X] = σ 2 . That is, X1,..., Xn  area random sample from the distribution of X , a random variable with mean µ and variance σ 2 .  Recall the definitions of the estimators of σ 2  from lecture,
the sample variance:          the sample variance with Bessel’s correction:   
In lecture, we also noted that these two estimators are related as:

a)  Let T bean arbitrary random variable with mean and variance E[T] and Var[T] respec-
tively. Write an expression for E [T2] in terms of E[T] and Var[T]. Hint: How is Var[T] related to the first and second moments of T?
b)  Given a random variable or a constant T , the following relationship holds:


You can take the above as given (no need to prove it). Use this expression to express n(2)
Hint: For what value of T does the lefthand side of the above become equal to n(2)?
c)  d σ 2 ? What does your answer from part a) tell you about E  in terms of µ and σ 2 ? How about

E [X2]?d) i(F)(o(o)ie(o)) ?(e)d(in)es(p)imat(rt c))o,rio(s)fσ(E)2[n]deif(q)uno(al)tt,oi,slit(e)sd(s)ownw(than)a~orrd ge(a)gative(ter th)ly(a)n)  o(σ)r2up(?)w(T)~ahrd(at)e) in(U)ser(ng)m(y)s(o)o(u)f(r) μ(an)and(swe)rσ2(t)o? pIs(a)rtσa, n(a)u(n)n(d)ia(h)se(e)d e(rela)imator of(onship be)σ2(tw)e,ea(n)nd(σ)n(2)ifano(nd)t , id(h)o(a)nwa(is E)rd[σr(])
upward biased?

3)  For this question, download cps .dta from Canvas.  The file cps .dta contains a data set which comes from the response to US Current Population Survey (CPS) in 2001, a large labor market survey.  This data set contains data on 8,891 individuals living in Boston and Chicago.  We want to use these data to compare the education levels of black and white individuals, and their employment outcomes.

a) A dummy variable for a condition takes value 1 if that condition is satisfied and takes value 0 otherwise. The data set contains a variable, education, which takes on four values (highschool dropouts, highschool graduates, some college, and college degree and more). Each of these education levels corresponds to a numeric value:  1, 2, 3, and 4 respectively (e.g. if someone has some college, the variable education will be 3).  Use the education variable to create a new dummy variable indicating some college or more (i.e., those in the some college category plus those in the college and more category). You can create an additional variable in the dataset by using the assignment syntax:  dfname$newvar <-  (code  to  define newvar), where dfname is the name of the variable representing your dataframe. You can creat代 写ECON 3720: Introduction to Econometrics Problem Set 02 Fall Semester 2024Statistics
代做程序编程语言e dummy variables using the ifelse function in R. E.g., if you stored your data set in the variable cps and want to name your variable somecol, you would type

cps$somecol  <-  ifelse(condition,  value  if  true,  value  if  false) . What fraction of respondents at least some college education?
b)  Carry out a two-sided t-test for whether the mean of your some college or more variable is the same for black and white individuals. You can do this with the t .test function in

R. NOTE: Read the documentation for the t .test function before attempting the rest of this problem set! Report the following:
i)  The mean of the variable for white individuals.
ii)  The mean of the variable for black individuals.
iii)  The difference in the means.
iv)  The t-statistic.
v)  The p-value for the null hypothesis that the two means are the same against the alternative hypothesis that they’re different (two-sided).
Do you find any evidence that this variable differs for white and black individuals in the CPS data?
c)  Calculate the t-statistics for the difference in means for the years of experience vari- able (yearsexp).  Do you find evidence that this variable differs significantly for black individuals compared to white individuals?
d)  Discuss your results from b) and c).  Why do your conclusions for the education and experience variable differ?  Why do we care about whether these variables look similar by race?
e)  Calculate the t-statistics for the difference in means for whether the individual has a job or not (employed).  Do you find any evidence that this variable differs significantly for white and black individuals?
f)  In light of your results from d) and e), what do you think we can conclude about racial discrimination in employment from the CPS data?

4)  Download the data set caschool .dta from Canvas.  It contains observations on all the 420 California school districts in 1999.  Among the variables are the reading and math scores for 5th graders, read_scr and math_scr.

a)  Carry out a two-sided t-test for the difference in means for the reading and math scores. The data are arranged differently to the previous data set. In the CPS data, black and white respondents were different observations. You were to test the difference in means for a single variable across these two subsets of observations.  Here you want to compare

the means for two separate variables among all the observations.  You can do this by using the following particular method associated with the t .test function:
t .test(dfname$col1,  dfname$col2, paired  =  TRUE,  . . .) ,where the  ... indicates the other arguments of the t .test function that you may want to utilize (or leave at their default values).  NOTE: the paired argument being set to TRUE is important here!b)  Carry out two-sided t-tests for whether average reading and math scores are equal to
650.  Do you find any evidence that the average reading and math scores are different from 650?
c)  Suppose instead of the 420 observations you had only a subsample with 42 districts.  Draw a random subsample of 42 observations from the observations from the school district data. You do this with the sample function in R. For example your code for the sampling part may look like the following:
#  Always  set  seed before using  random  sampling  functions . #  This  is  for  replication:   if  you  fix  the  seed  and  run
#  the  same  code  on  someone  else’s  machine,  you  should  get #  the  same  numbers .
#  Pick  a number  like  0  or  1  or  123  and  set  seed  to  that . set.seed(0)
#  df_rs:   randomly  sampled  rows  from  dataframe. . #  df_orig:    original  dataframe. .
# numrows_rs:   the number  of  rows  you want  in  df_rs.   df_rs  <-  df_orig[sample(nrow(df_orig), numrows_rs),  ]IMPORTANT: For this part of the problem, please include the set.seed(0) command in the above code snippet in your own code before running your code. If you re-run the parts of the problem including the df_orig[sample(nrow(df_orig), numrows_rs),  ] part, re-run it by first calling the seed setting code and then run the rest of your code. (You don’t have to copy all the verbose comments: you could have no comments (really bad practice) or a shorter version that is readable to you.)  Now carry out the t-tests for

whether reading and math scores are equal to 650 on your subsample in Stata. Do your results differ from those in part b)? If so, why?

         
加QQ：99515681  WX：codinghelp
