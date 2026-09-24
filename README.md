# Employee-age
<!DOCTYPE html>
<html>
<body>

<h2>Employee Age and Retirement Calculator</h2>

<form method="post">
    Employee Name:
    <input type="text" name="name"><br><br>

    Date of Birth:
    <input type="date" name="dob"><br><br>

    <input type="submit" name="calculate" value="Calculate">
</form>

<?php
if(isset($_POST['calculate']))
{
    $name = $_POST['name'];
    $dob = new DateTime($_POST['dob']);
    $today = new DateTime();

    $age = $today->diff($dob)->y;
    $retirementAge = 60;
    $remaining = $retirementAge - $age;

    echo "<h3>Employee Details</h3>";
    echo "Name: $name<br>";
    echo "Current Age: $age years<br>";

    if($remaining > 0)
        echo "Years Remaining for Retirement: $remaining years";
    else
        echo "Employee has reached retirement age.";
}
?>

</body>


output:
Employee Age and Retirement Calculator

Employee Name: Brindha
Date of Birth: 2004-06-15

Name: Brindha
Current Age: 22 years
Years Remaining for Retirement: 38 years
</html>
