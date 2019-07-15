Examples
========

Guess The Number Game
---------------------

```neutron
import "types";
import "io";
import "random::randrange";

is_not_win = true;
number = randrange(0, 100);
num_guesses = 0;

while (is_not_win) {
  guess = types::to_int(io::stdin(prompt="Enter A Number Between 0 and 100: "));
  if (guess == number) {
    io::print("You Win!");
    is_not_win = false;
  } else if (guess < number) {
    io::print("Too Low");
  } else if (guess > number) {
    io::print("Too High");
  }
}
```

Factorial Calculator
--------------------

```neutron
import "io::print";

x = 10;  // get factorial of 10
answer = 1;

while (x > 1) {
  answer = answer * x;
  x = x - 1;
}

print(answer);
```
