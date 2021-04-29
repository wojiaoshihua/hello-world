# ***Dynamic programming***

************

### First of all, let's take a look at the introduction from Baidu Baike. Here comes the link: [Dynamic programming](https://baike.baidu.com/item/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/529408?fr=aladdin).

### Then let's look at the difference between dynamic programming and greedy algorithms.

---------

> Given the premise 'A' of  problem size n. Give an unknown solution 'B' is solved.(We use 'An' to denote "the known condition of problem size n").

> At this point, if the problem scale is reduced to 0, that is, A0 is known, A0->B can be known.

- If an element is added from A0, the change process of A1 can be obtained. That is A0->A1; Then there is A1 > A2;A2-> A3;……;Ai->A1+1;This is the strict inductive reasoning, which is the mathematical induction that we often use;

- For AI + 1,only its last state AI is needed to complete the whole reasoning process(without a more ordered state). We call the first mock exam Markoff model. The corresponding reasoning process is called "greedy method".

  ******************

> However, AI and AI + 1 are often not necessary and sufficient conditions for each other. With the increase of I, the valuable premise information is less and less. We can not get the next state only from the previous state. Therefore, we can adopt the following scheme:

- {A1->A2}; {A1, A2->A3}; {A1,A2,A3->A4};……; {A1,A2,...,Ai}->Ai+1.This way is the second mathematical induction.
- For Ai + 1, all the preceding preorder states are needed to complete the reasoning process. The first mock exam is called the high order Markoff model. The corresponding reasoning process is called "dynamic programming".

--------------------------

The above two state transition diagrams are as follows:

![图片](https://images2015.cnblogs.com/blog/731104/201604/731104-20160409090651359-667895634.jpg)

---------------------

### Characteristics of problems that can be solved by dynamic gauge

> The problems that can be solved by dynamic programming generally have three properties.



| properties.                       |                           details                            |
| --------------------------------- | :----------------------------------------------------------: |
| Optimization principle            | If the solution of the subproblem contained in the optimal solution of the problem is also optimal, it is said that the problem has the optimal substructure, that is, it satisfies the optimization principle. |
| No aftereffect                    | No aftereffect: that is, once the state of a certain stage is determined, it will not be affected by the subsequent decision of the state. In other words, the process after a certain state will not affect the precious state, but only related to the current state. |
| There are overlapping subproblems | There are overlapping subproblems: the subproblems are not independent, and a subproblem may be used many times in the next stage of decision-making(This property is not a necessary condition for the application of dynamic programming, but without this property, dynamic programming algorithm has no advantage compared with other algorithms. |

------------------------

#### The steps of algorithm implementation(~~just common~~)

1. Create a one-dimensional array or two-dimensional array, and save the results of each subproblem. The specific creation of one-dimensional array or two-dimensional array depends on the title. Basically, if the title gives a one-dimensional array for operation, you can only create one-dimensional array for operation, you can only create one-dimensional array. If the title gives two one-dimensional arrays for operation or two different types of variable values. For example, the volume and total volume of different objects in the knapsack problem, the change of different denominations and the total amount of money in the change problem, so you need to create a two-dimensional array.
2. To set the boundary value of an array, one-dimensional array is to set the first number, and two-dimensional array is to set the values of the first row and the first column. In particular, rolling one-dimensional array is to set the values of the whole array, and then add and change to different values according to different data.
3. Find out the state transition equation, that is to say, find out the relationship between each state and its previous state, and write the code according to the state transition equation.
4. Return the required value,usually the last value of the array or the bottom right corner of the two-dimensional array.

#### Basic code framework:

```
for(j=1; j<=m; j=j+1) // the first stage
    xn[j] = initial value;
 
  for(i=n-1; i>=1; i=i-1)
    for(j=1; j>=f(i); j=j+1)
      xi[j]=j=max（or min）{g(xi-[j1:j2]), ......, g(xi-1[jk:jk+1])};
 
 t = g(x1[j1:j2]); // A scheme of solving the optimal solution of the whole //problem by the optimal solution of the subproblem
 
 print(x1[j1]);
 
 for(i=2; i<=n-1; i=i+1）
 {  
      t = t-xi-1[ji];
 
      for(j=1; j>=f(i); j=j+1)
         if(t=xi[ji])
              break;
              }
```









[README.md](/READEME.md)

