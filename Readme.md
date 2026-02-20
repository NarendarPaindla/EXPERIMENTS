# Experiment-5 menu.html after applying styles 

```html
<!DOCTYPE html>
<html>
<head>
    <title>Food Delivery</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #ff9966, #ff5e62);
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: #ffffff;
            padding: 30px 40px;
            border-radius: 12px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
            width: 350px;
        }

        h1 {
            text-align: center;
            color: #ff5e62;
            margin-bottom: 5px;
        }

        h3 {
            text-align: center;
            color: #555;
            margin-bottom: 20px;
        }

        .menu-item {
            margin: 10px 0;
            font-size: 16px;
        }

        label {
            font-weight: bold;
        }

        input[type="text"] {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            border-radius: 6px;
            border: 1px solid #ccc;
        }

        button {
            width: 100%;
            padding: 10px;
            background-color: #ff5e62;
            border: none;
            color: white;
            font-size: 16px;
            border-radius: 6px;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover {
            background-color: #e14b50;
        }
    </style>

</head>
<body>

    <div class="container">
        <h1>Spice Hub Restaurant</h1>
        <h3>Menu</h3>

        <form method="POST" action="/order">
            
            <div class="menu-item">
                <input type="radio" name="food" value="Biryani" required />
                Biryani - ₹200
            </div>

            <div class="menu-item">
                <input type="radio" name="food" value="Fried Rice" />
                Fried Rice - ₹150
            </div>

            <div class="menu-item">
                <input type="radio" name="food" value="Paneer Curry" />
                Paneer Curry - ₹180
            </div>

            <br>

            <label>Customer Name:</label>
            <input type="text" name="customer" required />

            <br><br>

            <button type="submit">Place Order</button>

        </form>
    </div>

</body>
</html>
```



# Meeting Link

[Meeting link](https://meet.google.com/nsm-mpeu-zhv)
