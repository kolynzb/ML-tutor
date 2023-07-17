**Decision Trees**

Decision trees are tree-based models that help in making a decision. They can be used in both regression and classification problems. To make a decision, they use a hierarchical structure and break the dataset into smaller subsets.

For example: Suppose there is a dataset using which you want to know the pollution levels in a city using some of its demographics.

Some of the features are industry, population temperature, etc. Now, as we keep on adding new features, generally non-linearity in the data increases and we cannot fit linear regression, for such cases we use non-linear models, like decision trees. 

If you make a decision tree for the above example, it would look like it as shown below.

![RT.PNG](https://olympus.mygreatlearning.com/courses/74509/files/4905716/preview?verifier=zUPZZpTKYx4iUPm4kFy1av6UT9TeqkYSZpEfKEdZ)  
The decision tree will make the first split where industry <748, the second split is where population<190, and similarly, the third and fourth split are where wet days<108  and temp<59.35 respectively.

After making a split 1 if industries are greater than 748, the pollution level is 67, else we make another split for population, and goes like that.  
This is the basic working principle of the decision tree. The next question is how regression trees make a split?

Formally, the decision tree split the data based on the below concept:

In theory, we can make any shape, but we choose to divide the space using high-dimensional rectangles or boxes because of the ease of simplicity and interpretation. The goal is to find boxes that minimize the RSS.

![](https://miro.medium.com/max/362/1*8DVvR_YW-wjMQelUXnEE6Q.png)

  

It is computationally infeasible to consider every possible partition of feature space into J boxes. So to overcome that we go for a _top-down, greedy_ approach known as _recursive binary splitting._ The approach is _top-down_ as it starts at the top of the tree ( at which all observations fall into a single region) and successively splits the predictor space into two new branches. It is _greedy_ because, at each step, it chooses the best split at that particular region and not for the next steps.

In order to perform Recursive binary splitting, we select the predictor and cut point that leads to the greatest reduction in RSS.

![](https://miro.medium.com/max/494/1*KDvqpB1b197VgffROzx3lw.png)

  

We seek the value of j and s that minimize the equation:

![](https://miro.medium.com/max/483/1*lC9tcsqZaVko67fzbFr86A.png)

**Important terminology**

1. **Root Node:** This attribute is used for dividing the data into two or more sets. The feature attribute in this node is selected based on Attribute Selection Techniques.
2. **Branch or Sub-Tree:** A part of the entire decision tree is called a branch or sub-tree.
3. **Splitting:** Dividing a node into two or more sub-nodes based on if-else conditions.
4. **Decision Node:** After splitting the sub-nodes into further sub-nodes, then it is called the decision node.
5. **Leaf or Terminal Node:** This is the end of the decision tree where it cannot be split into further sub-nodes.
6. **Depth of the tree:** The depth of a decision tree is the number of nodes from the root node down to the furthest leaf node. The below tree has a depth equal to 2.

![DT3.PNG](https://olympus.mygreatlearning.com/courses/74509/files/4905718/preview?verifier=dtNoYVRfqHDRzr0WAuSsNr9wZUs2xS6htbutN84c)