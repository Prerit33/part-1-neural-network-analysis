# part-1-neural-network-analysis

## Dataset Link - 
https://drive.google.com/drive/folders/1Aihn49cUYMjCgeCTFBTyprjrgZO3UY6r

## Task 6: 

1) *What role do weights and biases play in the model?* - Weights act as the "strength" of the connections between neurons. They dictate how much influence a specific input feature (like monthly_charges) has on the next layer. Through training, the network adjusts these weights to prioritize important features and ignore irrelevant ones.Biases act as an intercept (similar to $b$ in the linear equation $y = mx + b$). They shift the output of the activation function left or right. Without biases, a neural network would be forced to pass through the origin $(0,0)$, severely limiting its flexibility to fit real-world, complex data.
  
2) *Why is an activation function required?* - Activation functions (like ReLU or Sigmoid) introduce non-linearity into the network. If a neural network only used linear math (multiplying weights and adding biases), no matter how many hidden layers you added, the entire network would collapse into a single linear regression model. Activation functions allow the network to learn complex, curved, and intricate decision boundaries needed to solve advanced problems.
  
3) *What happens when the learning rate is too high or too low?* - The learning rate dictates how big of a "step" the optimizer takes when updating the weights during backpropagation.Too High: The model takes steps that are too large and overshoots the optimal minimum loss. The training process becomes unstable, and the model may completely fail to converge (the loss might even increase).Too Low: The model takes infinitesimally small steps. While it might eventually find the minimum, training will be agonizingly slow. It also risks getting permanently "stuck" in a local minimum, completely missing the global optimal solution.

4) *Did your model show signs of underfitting or overfitting?* - The model demonstrated a specific type of underfitting on the minority class, driven by severe data imbalance rather than traditional architectural flaws.It did not overfit, because the training accuracy (~98.5%) and testing accuracy (~98.5%) were practically identical. If it were overfitting, training accuracy would be near 100% while testing accuracy plummeted.However, because the dataset consisted of ~98.5% retained customers and only ~1.5% churned customers, the model quickly realized that the mathematical path of least resistance was to confidently predict "Retained" every single time. It failed to learn the underlying patterns of churning customers (evidenced by a Recall of 0.00), meaning it fundamentally underfit the problem we were actually trying to solve.
