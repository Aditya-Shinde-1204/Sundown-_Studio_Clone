# How to Run
# Banking API

This project is a simple **Flask-based Banking API** that supports customers, accounts, deposits, withdrawals, balance checks, and transaction logs.

---

## 🚀 Getting Started

### 1. Clone or Download the Project
Place `bank.py` and `transactions.log` in the same directory.

### 2. Create & Activate Virtual Environment (recommended)
```bash
python -m venv venv
venv\Scripts\activate      # Windows
```

### 3. Install Dependencies
```bash
pip install flask
```

### 4. Run the Flask App
```bash
python bank.py
```
By default, the API will run at:
```
http://127.0.0.1:5000
```


## API Endpoints

### 1. Create Customer
**POST** `/customers`  
Request Body:
```json
{
  "name": "John Doe"
}
```
Response:
```json
{
  "customer_id": "cust_1",
  "name": "John Doe"
}
```

---

### 2. Create Account
**POST** `/accounts`  
Request Body:
```json
{
  "customer_id": "cust_1",
  "initial_balance": 5000
}
```
Response:
```json
{
  "account_number": "acc_1",
  "customer_id": "cust_1",
  "balance": 5000
}
```

---

### 3. Deposit
**POST** `/accounts/<account_number>/deposit`  
Example: `/accounts/acc_1/deposit`  
Request Body:
```json
{
  "amount": 500
}
```
Response:
```json
{
  "account_number": "acc_1",
  "new_balance": 5500,
  "message": "Deposit successful"
}
```

---

### 4. Withdraw
**POST** `/accounts/<account_number>/withdraw`  
Example: `/accounts/acc_1/withdraw`  
Request Body:
```json
{
  "amount": 1000
}
```
Response:
```json
{
  "account_number": "acc_1",
  "new_balance": 4500,
  "message": "Withdrawal successful"
}
```

---

### 5. Get Balance
**GET** `/accounts/<account_number>/balance`  
Example: `/accounts/acc_1/balance`  
Response:
```json
{
  "account_number": "acc_1",
  "balance": 4500
}
```

---

### 6. Get Transactions
**GET** `/accounts/<account_number>/transactions`  
Example: `/accounts/acc_1/transactions`  
Response:
```json
{
  "account_number": "acc_1",
  "transactions": [
    {
      "type": "deposit",
      "account_number": "acc_1",
      "amount": 500,
      "timestamp": "2025-08-17T20:54:11.000000"
    }
  ]
}
```

---

## 📝 Transaction Logs
All transactions are also logged in `transactions.log`, for example:
```
2025-08-17 20:50:57 - INITIAL_DEPOSIT - Account: acc_1 - Amount: 5000.00
2025-08-17 20:54:11 - DEPOSIT - Account: acc_1 - Amount: 500.00
2025-08-17 20:57:34 - WITHDRAWAL - Account: acc_1 - Amount: 3000.00
```

✅ You can now test all APIs in **Postman** by sending requests to `http://127.0.0.1:5000`.
