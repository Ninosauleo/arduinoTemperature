# arduinoTemperature
Temperature meter based on an Arduino Computer Board 

## Components
1 Arduino Uno CPU board
1 Dual 7 segment digit display
1 Resistance net in a DIL ( 7x0.68 kOhm)
1 Temperature sensor
1 4 bits code switch (For extended function)


a) Basic version
In a loop structure:
- Read the analog value from temp sensor through AD channel A0
- Calculate the temperature and then the pattern for the digits.
- Write out to one digit
- Delay.
- Write out to the other digit
- Delay

You should use one digital Out bit for each of the digits segments ( #7) . Set bits pattern for the digit
nr (0-9). High bit value will light up the actual segment. Chose digit to light up by the two additional
out bits (8-9). One of these two bits low will turn selected digit on.
Try to read the analog input at least with a frequency of 10 Hz and to find a frequency for the
displaying of each digit to give a readable value.


b) Extended version
Try to extend the function with the following:
By use of a 4 bit code switch (we can use less than four) connected to some digital in bits ( 10 - 12 )
we can read a in code depending on the selection from user binary 0 to F ( if four bits). We can use
the in value to select one of several possible function modes. In our case we just will have two
modes; code zero basic mode and code x max temp mode.
Extend the basic version of the program with this extended mod.
Note: The code switch connect the c-pin to the pins (1,2,4,8 ) that have a zero value for the
corresponding bit pattern. ( Ex: for position 3 there is connection between c and 4 and 8.
