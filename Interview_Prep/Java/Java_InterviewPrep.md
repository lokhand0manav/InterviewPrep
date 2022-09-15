- https://github.com/learning-zone/java-interview-questions
	- https://github.com/learning-zone/java-interview-questions/blob/master/java-multiple-choice-questions-answers.md
- [[Wissen_Interview_prep_checkList]]
- https://www.geeksforgeeks.org/java-multiple-choice-questions/
- My Interview Experience at Morgan Stanley R1:
	- what will happen in serialization when we have transient , String and a static variable.
	- if you have overloaded a method, one taking Object and another taking String as parameters, and you call the method with null value passed, which will get called.
	- Can you override a method with different return type (Yes)
	- Can you overload methods with different return type (No)
	- Write a code to reverse a String in java without using reverse method of stream
	- Write a code to find the frequency of the characters in Spring
		- Find the first character with no repeatation
	- Find the dissection point of 2 lists. <-- means there is only one number which is common in both the list, we have to find the index of them. (I actually used brute force, but need to find the elegant solution)
- Morgan Stanley Java + Angular:
	- String with {abc{cd}}    index => 0    Output : index => 8
		- Input index will be opening brace closing will be its corresponding closing
	- Integer : output in wave form    `int[] = { 1,4,2,6,7,8,9,3,}`    `output[] = { 1,4,2,6,3,9,7,8}`  
    `1,2,3,4,6,7,8,9    9,8,7,6,4,3,2,1  
    `1,9,2,8,3,7,4,6`
	    - sort the integer and print first and last and increament and decreament: 
	`public static void main(String[] args) {`
	    `Integer[] value = new Integer[]{1,4,2,6,7,8,9,3,10};  `
	    `Arrays.sort(value);  `
	    `int i1 = 0,i2 = value.length-1;  `
	    `while( i1<=i2 ){  `
	        `if(i1!=i2){  `
	            `System.out.print(", "+value[i1]+", "+value[i2]);  `
	        `}else{  `
	            `System.out.print(", "+value[i1]);  `
	        `} ` 
	        `i1++;  `
	        `i2--;  `
`	}  `
`}`