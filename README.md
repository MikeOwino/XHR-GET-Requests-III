# XHR-GET-Requests-III
By this point, you have an idea of how to write the boilerplate code for an AJAX request using an XHR object.  In this exercise, you will incorporate that boilerplate code to make a GET request to the Datamuse API to search for words that rhyme!


#### QQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQ

At the top of main.js, create a const named url and save to it the following URL (as a string):

https://api.datamuse.com/words?
You’ll be using this URL to direct your request.

Checkpoint 2 Passed

Hint
The syntax will look something like:

const nameOfVariable = 'a string of sorts';
2.
Underneath const url, create another const named queryParams and assign it to 'rel_rhy='

'rel_rhy=' is the start of a parameter for the query string. This parameter will narrow your search to words that rhyme.

Checkpoint 3 Passed

Hint
The syntax will look like:

const nameOfVariable = 'a string of sorts';
3.
In the function getSuggestions(), create a const named wordQuery and assign it to be inputField.value.

inputField.value grabs what is in the inputField and assigns it to the variable wordQuery.

You’ll be working in getSuggestions() for the rest of the exercise.

Checkpoint 4 Passed

Hint
Make sure you’re inside the code block of getSuggestions().

4.
Now create another const named endpoint, and assign equal to a string that concatenates url, queryParams, and wordQuery.

endpoint will store the value of the entire URL and query string.

Checkpoint 5 Passed

Hint
There are many ways of concatenating strings; take a look at the following examples:

const word1 = ‘hello’;
const word2 = ‘world!’;
 
console.log(word1 + ' ' + word2);
// ‘hello world!’
You can also interpolate it using a template literal, but remember to use backticks!

console.log(`${word1} ${word2}`);
// ‘hello world!’
5.
You can now start on the XMLHttpRequest object. Declare a const named xhr and use the new operator to create the XMLHttpRequest object.

Checkpoint 6 Passed

Hint
Make sure you’re still inside the code block of getSuggestions(). The syntax will look like:

const xhr = new XMLHttpRequest();
6.
Set the responseType of xhr to 'json'.

When data is sent back, it will be in JSON format.

Checkpoint 7 Passed

Hint
Make sure you’re in the code block for getSuggestions().

To access the .responseType property of xhr, use dot notation like: xhr.responseType. Then assign it a value of ‘json’. The syntax for this would look like:

xhr.responseType = 'json';
7.
Assign an anonymous arrow function to the onreadystatechange event handler of xhr.

Checkpoint 8 Passed

Hint
You can think of the onreadystatechange event handler as another property. Use dot notation to access it and assign it to an anonymous arrow function.

To access onreadystatechange using dot notation, use the following syntax:

xhr.onreadystatechange 
Then, to assign it an anonymous arrow function:

xhr.onreadystatechange = () => {
  // Event handler code
}
8.
Include the following code inside the code block of the anonymous arrow function you just created:

if (xhr.readyState === XMLHttpRequest.DONE) {
  renderRawResponse(xhr.response)
}
The renderRawResponse() helper function can be viewed at public/helperFunctions.js.

Checkpoint 9 Passed
9.
Below the anonymous arrow function you just created (but still inside of getSuggestions()), call the .open() method on the XHR object and pass it 'GET' and endpoint as respective arguments. This method call will create a new request using the two arguments: 'GET' sets the method and url sets the destination.

Underneath .open(), call the .send() method on xhr and pass it no arguments. The .send() method will send the request to the server.

Then run your code.

Type in a word in the input field and click the submit button. If all went well, the response field in the browser will display the raw response from the API!

Checkpoint 10 Passed

Hint
Make sure you’re not in the anonymous arrow function code block.

.open() takes two arguments—the first one is 'GET', and the second is endpoint.

.send() goes on the line after .open() and doesn’t take any arguments.

10.
Now delete renderRawResponse(xhr.response) and replace it with renderResponse(xhr.response) and run your code.

Then type in a word in the input field and click the submit button.

Great, now it looks nice and formatted!
