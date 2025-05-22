<!DOCTYPE html>
<html lang="en">
<head>
    <meta Dennis="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Storefront Tracker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f5f5f5;
        }
        header {
            background-color: #8b34d3;
            color: white;
            padding: 5px;
        }
        .container {
            margin: 22px auto;
            padding: 20px;
            background-color: rgb(255, 255, 255);
            border-radius: 15px;
            width: 50%;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
        }
        input, button {
            margin: 15px;
            padding: 15px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Storefront Income & Expense Tracker</h1>
    </header>
    <div class="container">
        <h2>Log Transaction</h2>
        <label>Transaction Type:</label>
        <select id="transactionType">
            <option value="income">Income</option>
            <option value="expense">Expense</option>
        </select>
        <br>
        <input type="text" id="amount" placeholder="Enter amount" />
        <br>
        <button onclick="logTransaction()">Save</button>
        <h2>Transaction Summary</h2>
        <p id="summary">Total Income: 0 | Total Expense: 0</p>
    </div>

    <script>
        let totalIncome = 0;
        let totalExpense = 0;

        function logTransaction() {
            let type = document.getElementById("transactionType").value;
            let amount = parseFloat(document.getElementById("amount").value);

            if (!isNaN(amount)) {
                if (type === "income") {
                    totalIncome += amount;
                } else {
                    totalExpense += amount;
                }
                document.getElementById("summary").textContent = `Total Income: ${totalIncome} | Total Expense: ${totalExpense}`;
            }
        }
    </script>
</body>
</html>
