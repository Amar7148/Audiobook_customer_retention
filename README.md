# Audiobook Customer Retention Prediction

This project predicts whether a customer of an audiobook app will purchase again within the next 6 months, based on their activity and engagement data from the past 2 years.

## Dataset

The dataset (`Audiobooks_data.csv`) contains:

- Book length overall (sum of minutes of all purchases)
- Book length avg (average minutes per purchase)
- Price paid overall (sum of all purchases)
- Price paid avg (average price per purchase)
- Review (boolean if customer left a review)
- Review score (0–10 if review left)
- Total minutes listened
- Completion (0–1)
- Support requests (number of support tickets)
- Last visited minus purchase date (days)

**Target variable**:  
- `1` → Customer purchased again within 6 months  
- `0` → Customer did not purchase again  

## Preprocessing

- Removed Customer ID  
- Balanced dataset (equal 0s and 1s)  
- Standardized inputs  
- Shuffled dataset  
- Split into Train (80%), Validation (10%), Test (10%)  
- Saved processed data as `.npz` files  

## Model

- Input: 10 features  
- 2 hidden layers (Dense(50, ReLU))  
- Output: Dense(2, Softmax)  
- Loss: `sparse_categorical_crossentropy`  
- Optimizer: Adam  
- Batch size: 100  
- Epochs: 100 (with early stopping)  

## Results

- Validation accuracy: ~87%  
- Test accuracy: 84.38%
