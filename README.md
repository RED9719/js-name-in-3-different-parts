# js-name-in-3-different-parts
Develop and demonstrate a HTML file that includes JavaScript script for taking full name in a 
text field and display first, middle, last name *in 3 different labels. Middle and last name may be 
optional, thus messages like "NA" should be displayed in corresponding labels. If input contains 2 
words, then they should be considered as first and last names. 

<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Full Name Parser</title>
</head>
<body>
    <div class="container">
        <h2>Full Name Parser</h2>
        <div class="form-group">
            <label for="full-name">Enter Full Name:</label>
            <input type="text" id="full-name" onkeyup="parseFullName()">
        </div>
        <div class="result">
            <label>First Name: <span id="first-name">NA</span></label><br>
            <label>Middle Name: <span id="middle-name">NA</span></label><br>
            <label>Last Name: <span id="last-name">NA</span></label>
        </div>
    </div>

    <script>
        function parseFullName() {
            const fullName = document.getElementById('full-name').value.trim();
            const nameParts = fullName.split(/\s+/);

            const firstName = nameParts[0] || "NA";
            const middleName = nameParts.length > 2 ? nameParts.slice(1, -1).join(' ') : "NA";
            const lastName = nameParts.length > 1 ? nameParts[nameParts.length - 1] : "NA";

            document.getElementById('first-name').innerText = firstName;
            document.getElementById('middle-name').innerText = middleName;
            document.getElementById('last-name').innerText = lastName;
        }
    </script>
</body>
</html>
