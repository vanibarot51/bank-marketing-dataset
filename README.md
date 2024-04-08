## Bank Marketing Dataset

The dataset you will use comes from the UCI Machine Learning repository Links to an external site.. The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. 

I have used bank-additional-full.csv file for this exercise from the zip folder because it felt like it had more data in terms of columns and rows too.

Column details:
1. age (numeric)
2. job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
3. marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
4. education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
5. default: has credit in default? (categorical: 'no','yes','unknown')

6. housing: has housing loan? (categorical: 'no','yes','unknown')

7. loan: has personal loan? (categorical: 'no','yes','unknown')

8. contact: contact communication type (categorical: 'cellular','telephone')

9. month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')

10. day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')

11. duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.

12. campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

13. pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)

14. previous: number of contacts performed before this campaign and for this client (numeric)

15. poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

16. emp.var.rate: employment variation rate - quarterly indicator (numeric)

17. cons.price.idx: consumer price index - monthly indicator (numeric)
18. cons.conf.idx: consumer confidence index - monthly indicator (numeric)
19. euribor3m: euribor 3 month rate - daily indicator (numeric)
20. nr.employed: number of employees - quarterly indicator (numeric)

21. y - has the client subscribed a term deposit? (binary: 'yes','no')(target variable)

The goal of this exercise is to compare the performance of the classifiers (k-nearest neighbors, logistic regression, decision trees, and support vector machines)

Starting with k-nearest neighbors:
I choose n_neighbors value from 1 to 20 to get the best fit for n_neighbor. The all calculation of 1 to 21 is in coding file. The best fit turned out to be n_neighbor = 19, since it has the best testing score. The score is : 0.9110420510828396

the next classifier I chose to perform is DecisionTree with depth : None to 20. The depth at 5 gives the best testing score: 0.9124502282218122

Later I used LogisticRegression classifier. I tried to use degree 1 to 20 but sadly my system froze and so I had to use without degree and that gave testing score: 0.9094882004467321 

Lastly I used classification SVC with linear and rbf. The best testing score I get is with linear type kernel: 0.9018160629309507. 

When compared the best testing score it is with DecisionTree with depth 5, it's 0.9124502282218122 but KNN test score with n_neighbor 19 is very close : 0.9110420510828396 and has less avg. time than decision tree which is surprisingly 0.0000.

Hence KNN with n_neighbor=19 will be the best to perform classification on bank marketing dataset.
