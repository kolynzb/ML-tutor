### **What is bootstrapping?**

Bootstrapping is a statistical procedure that **resamples a single dataset** to create **many simulated samples.**

### **How do we perform bootstrapping?**

We perform bootstrapping using sampling with replacement method, where each sample is called a "Bootstrap Sample".

In sampling with replacement, we draw an item randomly from the population and put it back into the population before drawing the next item, i.e., each item has an equal chance of getting selected every time we draw an item. Hence, one item can be selected multiple times in a particular sample.

In bootstrapping, the number of records in each bootstrap sample can be smaller than or equal to the total number of records in the original data.

**Let's consider an example of a bootstrap sample on dummy data:** The below image shows bootstrap samples created from the original dataset. Let's say in our case, we want 3 records in each bootstrap sample.

![bootstrap-1.png](https://olympus.mygreatlearning.com/courses/74509/files/6958170/preview?verifier=wfMkfUHEEn3paHy6XR2A5MMJODKqAhmpPSwKzf91)

In the above image, we can see that 3 records have been randomly sampled to create a bootstrap sample and here the record with index 7 is repeated 2 times in the bootstrap sample.

![bootstrap-2.png](https://olympus.mygreatlearning.com/courses/74509/files/6958169/preview?verifier=2jmUvaJTtmeE2THsV36yc2lfWhEzYPAkCH7QoxYB)

In the above image, we can see that 3 records have been randomly sampled to create a bootstrap sample and here the record with index 5 is repeated 2 times in the bootstrap sample.

![bootstrap-3.png](https://olympus.mygreatlearning.com/courses/74509/files/6958168/preview?verifier=GoTVoDL2c82aqNPw2Wj9ZF12cGvVf2yGWPP61mbZ)

In the above image, we can see that 3 records have been randomly sampled to create a bootstrap sample and all the records are unique.
