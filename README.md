# Binary-decimal-conversion
Decimal to binary and binary to decimal conversion without using native Javascript converters, string or arrays.

## To Binary
Given a decimal number like 100, 200... convert it into binary 1100100, 11001000 without using any native methods like `Number.toString()`, `string` or `array`.

```
function toBinary(number) {

		let result = 0;
		let i = 0;

		/*
			Loop through the number by dividing it by 2 until we reach 1 or below
		*/
		while(number >= 1) {
			let reminder = number % 2;
			if (reminder) {
				/* 
					If the reminder is 1 we add it to the power of 10 to get the 
					place value. ie. 100, 1000 ... 
				*/
				result += Math.pow(10, i);
			}
			/* 
				Increment the i value
				Reduce the number by dividing it by 2
			*/
			i++;
			number = Math.floor(number / 2);
		}

		return result;
	}

	console.log('To Binary:');
	console.log('100 -> ', toBinary(100)); // 1100100
	console.log('500 -> ', toBinary(500)); // 111110100
```

## To Decimal
Given a binary number like 1100100, 11001000 convert it into binary 100, 200... without using any native methods like `Number.toString()`, `string` or `array`.

```
function toDecimal(number) {
		
		let result = 0;
		let i = 0;

		/*
			Loop through the number by dividing it by 10 until we reach 0 or below
		*/
		while(number > 0) {
			let reminder = number % 10;
			if (reminder) {
				/* 
					Get the last digit of the binary number and if it is 1,
					then add it to the result by 2 to the power of the i.
				*/
				result += Math.pow(2, i);
			}
			/*
			 	Increment the i in every iteration.
			 	reduce the number by 10.
			*/
			i++;
			number = Math.floor(number / 10);
		}
		return result;
	}
	
	console.log('To Decimal:');
	console.log('1100100 -> ', toDecimal(1100100)); // 100
	console.log('111110100 -> ', toDecimal(111110100));	 // 500
  ```
