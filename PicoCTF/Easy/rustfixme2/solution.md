# Solution

``` 
 fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &String){ // How do we pass values to a function that we want to change?
```
To allow functions to modify values we use mutable references.

We first have to declare the value we intend to change as **mut**

in this case we want to modify the value _string_ 

``` 
 fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string:&mut String){ 
```
now we proceed to the other clues

```
let party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
```

again we simply have to declare the values _mut_
```
let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
```

after doing **cargo build** and **cargo run** you get this flag: <mark>_picoCTF{4r3_y0u_h4v1n5_fun_y31?}_</mark>