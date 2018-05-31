# Lowell
Lowell is a PHP libary for checking if a give phone number is a premium rate or not. Premium rate numbers provide an attack vector by exploiting two-factor auth validation steps to generate the attacker money at your expense. 

## Example
```
$checker = new Lowell("en_GB");
$okay = $checker->check("118 118");

if(!$okay) {
  print "Sorry, that number is not valid";
} else {
  print "Yay. All good.";
}
```

If you like you can have Lowell throw an error if the number isn't okay.

```
try {
    $checker = new Lowell("en_GB");
    $number = $checker->checkOrFail("118 118");
    
    // do something with your number.
} catch(NumberNotValid) {
    print "Sorry, that number is not valid";
}
```
