# [GOOGLE APP DATA ANALYSIS ](/9lRMLcbMR--joBvR84z5KA)
---
## [ 1. OVERVIEW ](/9lRMLcbMR--joBvR84z5KA)

[ **- About the data**: ](/9lRMLcbMR--joBvR84z5KA) Nowadays we get a large amount of data in various format from csv to img. However as a human, we can effectily read and make decision with these data showed as bar, graph. This is a short version of how I cleaning up the data and visualize them to get usefull insights.
[ **- What you can expect in this github**: ](/9lRMLcbMR--joBvR84z5KA) 
1. The code of cleaning up the data
2. Sample of how to visualize data 
3. Which questions to ask to draw insights from the data.
![](https://i.imgur.com/HvgJVic.png)

---
## [ 2. THE APPROACH ](/9lRMLcbMR--joBvR84z5KA)

### [2.1 Code approach](/lH2ryznwTJa4oKA092dkkA)
- There are 2 main coding parts in this demo:

| Cleaning code | Vsualization code | 
| -------- | -------- | 

#### [2.1.1 Cleaning code](/lH2ryznwTJa4oKA092dkkA)

**- 1st: The very first and foremost thing to be done in order to visualize them.**
- After studying the data, I got to deal with the missing values, the wrong format first.
![](https://i.imgur.com/7PbmROy.png)

![](https://i.imgur.com/7S3N3En.png)

**Sample code for cleaing the data:**
```
# we remove all the character and replace ones without size with NaN for the purpose of easy dropping
data['Size'] = data['Size'].apply(lambda x: x.replace('M', '') if 'M' in str(x) else x)
data['Size'] = data['Size'].apply(lambda x: x.replace('Varies with device', 'NaN') if 'Varies with device' in str(x) else x)
data['Size'] = data['Size'].apply(lambda x: float(x.replace('k', ''))/1000 if 'k' in str(x) else x)
data['Size'] = data['Size'].apply(lambda x: x.replace('+', '') if '+' in str(x) else x)
data['Size'] = data['Size'].apply(lambda x: x.replace(',', '') if ',' in str(x) else x)
```

#### [2.1.2 How to start analyzing the data](/lH2ryznwTJa4oKA092dkkA)

##### 1. Raising the questions that we want the answer from the data first.
- **1. Which is the dominate content rating on Google App store?**

![](https://i.imgur.com/Z7hdqzE.png)

- **2. What is the distribution of categories on Google apps?**
![](https://i.imgur.com/NzoSXFg.png)
![](https://i.imgur.com/Zsxw2Rb.png)

- **3. What can the app size tell us?**
![](https://i.imgur.com/3t8Gr6X.png)

- **4. Are there more free or paid apps on Google?**
![](https://i.imgur.com/5MySrCg.png)

---

## [3. Conclusion ](/-iz_-FrPQ3SPbl7WJxdocg)

- **Data is surely a powerfull tool for us to learn insights.** But data alone may not be enough, in this demo version, I pointed out that add a little power of Python code, we can make easier to make the right decisions.

- **Hope you enjoy the code**


