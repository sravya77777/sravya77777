<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Online Harassment Reporting Dashboard</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <h1>Report Online Harassment</h1>
    <form method="post" enctype="multipart/form-data">
        <label for="report_text">Incident Description:</label><br>
        <textarea name="report_text" required rows="5" cols="40" placeholder="Describe the incident..."></textarea><br>
        <label for="attachment">Upload Evidence (screenshot, etc.):</label>
        <input type="file" name="attachment" accept="image/*,application/pdf"><br><br>
        <button type="submit">Submit Report</button>
    </form>
    {% with messages = get_flashed_messages(with_categories=true) %}
      {% if messages %}
        {% for category, message in messages %}
          <div class="flash {{ category }}">{{ message }}</div>
        {% endfor %}
      {% endif %}
    {% endwith %}
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Report Submitted</title>
</head>
<body>
    <h2>Your report has been securely submitted.</h2>
    <p>Thank you for your courage. If you need further support, consider contacting a local helpline or law enforcement.</p>
    <a href="{{ url_for('index') }}">Submit another report</a>
</body>
</html>
