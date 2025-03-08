# **Scikit-Learn Pipelines**

## **What is a Pipeline?**
A **Pipeline** in Scikit-Learn is a tool that automates and streamlines the **data preprocessing and model training process** by chaining multiple steps together. It ensures that transformations are applied consistently across both training and test data while simplifying code and reducing errors.

## **Why Use Pipelines?**
- **Ensures consistency** in data preprocessing across training and testing.
- **Avoids data leakage** by applying transformations only on training data and using fitted parameters for testing.
- **Improves code readability** and maintainability.
- **Works seamlessly with GridSearchCV** for hyperparameter tuning.

## **How Does a Pipeline Work?**
A Pipeline consists of a sequence of steps, each performing a transformation or modeling operation. The final step is always an **estimator (model)**.
