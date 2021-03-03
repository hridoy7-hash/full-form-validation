# full-form-validation

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
<form method="post" action="<?php echo ($_SERVER['PHP_SELF']);?>">

<table>
<tr>
<td>Name</td>
<td><input type="text" name="name" placeholder="User Name"></td>
</tr>
<tr>
<td>Email</td>
<td><input type="email" name="email" placeholder="User Email"></td>
</tr>
<tr>
<td>Website</td>
<td><input type="text" name="website" placeholder="Enter Your Website"></td>
</tr>
<tr>
<td>Comment</td>
<td><textarea name="comment" id="" cols="30" rows="4"></textarea></td>
</tr>
<tr>
<td>Gender</td>
<td>
<input type="radio" name="gender" value="Female"/>Female
<input type="radio" name="gender" value="male"/>male
</td>
</tr>
<tr>
<td></td>
<td><input type="submit" name="submit" value="submit"></td>
</tr>
</table>
</form>
</body>

<?php

if($_SERVER["REQUEST_METHOD"]=="POST"){
    $name= Vaidation($_POST["name"]);
    $email= Vaidation($_POST["email"]);
    $website= Vaidation($_POST["website"]);
    $comment= Vaidation($_POST["comment"]);
    $gender= Vaidation($_POST["gender"]);
    

    echo "Name:".$name;
    echo "<br/>";
    echo "email:".$email;
    echo "<br/>";
    echo "website:".$website;
    echo "<br/>";
    echo "comment:".$comment;
    echo "<br/>";
    echo "gender:".$gender;
    }
function Vaidation($data) {
$data= trim($data);
$data= stripcslashes($data);
$data= htmlspecialchars($data);
return $data;
}
?>
</html>
