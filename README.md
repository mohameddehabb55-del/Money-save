<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>Money</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            direction: rtl;
        }

        .container {
            background: white;
            padding: 25px;
            width: 300px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            text-align: center;
        }

        h1 {
            color: #2c3e50;
        }

        .balance {
            font-size: 24px;
            margin: 15px 0;
            color: green;
        }

        input {
            width: 90%;
            padding: 8px;
            margin: 8px 0;
            font-size: 16px;
        }

        button {
            width: 90%;
            padding: 10px;
            margin: 5px 0;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .add {
            background: #27ae60;
            color: white;
        }

        .withdraw {
            background: #e67e22;
            color: white;
        }

        .reset {
            background: #c0392b;
            color: white;
        }

        button:hover {
            opacity: 0.9;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>💰 ادخار الأموال</h1>

    <div class="balance">
        الرصيد: <span id="balance">0</span> جنيه
    </div>

    <input type="number" id="amount" placeholder="أدخل المبلغ">

    <button class="add" onclick="addMoney()">➕ إضافة ادخار</button>
    <button class="withdraw" onclick="withdrawMoney()">➖ سحب مبلغ</button>
    <button class="reset" onclick="resetBalance()">🔄 تصفير الرصيد</button>
</div>

<script>
    let balance = 0;

    function addMoney() {
        let amount = Number(document.getElementById("amount").value);
        if (amount > 0) {
            balance += amount;
            updateBalance();
        } else {
            alert("من فضلك أدخل مبلغ صحيح");
        }
    }

    function withdrawMoney() {
        let amount = Number(document.getElementById("amount").value);
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            updateBalance();
        } else {
            alert("المبلغ غير صحيح أو الرصيد غير كافٍ");
        }
    }

    function resetBalance() {
        balance = 0;
        updateBalance();
    }

    function updateBalance() {
        document.getElementById("balance").innerText = balance;
        document.getElementById("amount").value = "";
    }
</script>

</body>
</html>
