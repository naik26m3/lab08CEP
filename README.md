# Lab 08 CEP

**Student Name: Tuan Khai Ngo**<br>
**Student ID: 138840244**

## My simple network diagram:
![Network Diagram](https://github.com/naik26m3/lab08CEP/blob/e77e973a7ef1c2a5e606b97acba02d416e1ef16b/network_diagram.png)

## Part A: Training Phase:

**Weight tracker (before training):**

|Feature|Tokens(weight)|
|-------|--------------|
|Food   |🍗            |
|Service|🍽️            |
|Price  |💰            |

### Training each card:

**Card 1**  
- **Food:** Great  
- **Service:** Poor  
- **Price:** Cheap    

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅  
**Weight Change:** None

**Card 2**  
- **Food:** Bad  
- **Service:** Great  
- **Price:** Expensive  

**Prediction:** LIKE<br>
**Actual:** DISLIKE<br>
**Correct?** ❌

**Weight Change:** +1 to Price

**Weight tracker:**
|Feature|Tokens(weight)|
|-------|--------------|
|Food   |🍗            |
|Service|🍽️            |
|Price  |💰💰         |

**Card 3**  
- **Food:** Good  
- **Service:** Okay  
- **Price:** Moderate  

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅  

**Card 4**  
- **Food:** Poor  
- **Service:** Poor  
- **Price:** Cheap  

**Prediction:** DISLIKE  
**Actual:** DISLIKE  
**Correct?** ✅  

**Card 5**  
- **Food:** Excellent  
- **Service:** Excellent  
- **Price:** Expensive  

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅  

**Card 6**  
- **Food:** Okay  
- **Service:** Bad  
- **Price:** Moderate  

**Prediction:** LIKE  
**Actual:** DISLIKE  
**Correct?** ❌  
**Weight Change:** +1 to Food  

**Weight tracker:**  
|Feature|Tokens(weight)|
|-------|--------------|
|Food   |🍗🍗          |
|Service|🍽️            |
|Price  |💰💰         |

**Card 7**  
- **Food:** Great  
- **Service:** Okay  
- **Price:** Cheap  

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅  

**Card 8**  
- **Food:** Poor  
- **Service:** Excellent  
- **Price:** Expensive  

**Prediction:** DISLIKE  
**Actual:** DISLIKE  
**Correct?** ✅  

**Card 9**  
- **Food:** Excellent  
- **Service:** Poor  
- **Price:** Moderate  

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅  

**Card 10**  
- **Food:** Okay  
- **Service:** Okay  
- **Price:** Expensive  

**Prediction:** DISLIKE  
**Actual:** DISLIKE  
**Correct?** ✅  

### Track Learning:

**Weight tracker (after training):**  
|Feature|Tokens(weight)|
|-------|--------------|
|Food   |🍗🍗          |
|Service|🍽️            |
|Price  |💰💰         |

**1. Which weights changed**
- Food: 2 tokens (before: 1 tokens)
- Service: 1 token (before: 1 tokens)
- Price: 2 tokens (before: 1 tokens)

**2. Correct predictions**

Card 1: ✅  
Card 2: ❌  
Card 3: ✅  
Card 4: ✅  
Card 5: ✅  
Card 6: ❌  
Card 7: ✅  
Card 8: ✅  
Card 9: ✅  
Card 10: ✅

**3. Observe improvement:**
- After 6 test cards, there are some incorrect predictions but it helps to adjust the weight.
- By the end of 10 test cards. Most predictions are correct.

## Part B: Testing Phase

**Card 11**  
- **Food:** Good  
- **Service:** Excellent  
- **Price:** Cheap  

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅  

**Card 12**  
- **Food:** Bad  
- **Service:** Bad  
- **Price:** Expensive  

**Prediction:** DISLIKE  
**Actual:** DISLIKE  
**Correct?** ✅  

**Card 13**  
- **Food:** Excellent  
- **Service:** Great  
- **Price:** Moderate  

**Prediction:** LIKE  
**Actual:** LIKE  
**Correct?** ✅

### Comparison

**Who improved the most?**  
- My predictions became more accurate after adjusting the weight during training phase.

**Which features were most important?**  
- Food and Price were one of the most important because both of them have 2 tokens which can be useful to know if the customer like the restaurant or not.

## Reflection Discussion
**1. How did your predictions improve?**
- In the beginning, there were some error during traning phase. But it helped me alot to adjust my weight tracker. Because of it, I improve my predictions a lot.

**2. How did "weights" (tokens) help you learn?**  
- It helps me know that the more tokens the more important it is. This is nearly the same as how neural networks adjust weight during learning phase.

**3. What would happen with more layers or inputs?**  
- With more layers and inputs, the weight tracker would be more complex which allow AI to learn more complex, and recognize different pattern.

**4. How does this reflect how real AI works?**  
- Real AI also learn and adjust weight based on the feedbacks but in a more complex data not just Food, Service and Price.



