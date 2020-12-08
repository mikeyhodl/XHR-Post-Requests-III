# XHR-Post-Requests-III

Reminder: If you haven’t already signed up for an API Key from Rebrandly, please read our Rebrandly URL Shortener API article. Keep in mind, while it’s ok to use your API key in these exercises, you should not share your key with anyone (not even if asking a question in the forums)!

In this exercise, you’ll be making a POST request to the Rebrandly API to shorten a URL.

Get ready! You’re now going to incorporate the previous lesson’s boilerplate code into making an actual POST request!

If you reset the exercise at any point, you will have to paste in your API key again at the top.

### QQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQ


1.
Copy your Rebrandly API Key, and assign it to the const apiKey at the top of your code.

Checkpoint 2 Passed
2.
Within the code block of shortenUrl(), create a const called urlToShorten, and save inputField.value to it. urlToShorten will now save the value of the input field

Note: for the remainder of this exercise’s instructions we will be working inside the code block of shortenUrl()!

Checkpoint 3 Passed

Hint
Make sure you’re inside the code block for shortenUrl().

3.
Create a const called data, and save the following code to it:

JSON.stringify({destination: urlToShorten});
We’re including this information because the API expects to see an object with a key destination that has a value of a URL.

Checkpoint 4 Passed

Hint
Make sure you’re inside the code block for shortenUrl().

data goes under urlToShorten.

4.
Create a new XMLHttpRequest object using the new operator, and save it to a const called xhr.

Checkpoint 5 Passed

Hint
The syntax will look like:

const xhr = new XMLHttpRequest();
5.
Set the responseType property of the xhr object to be 'json'.

Checkpoint 6 Passed

Hint
To access the responseType property of the xhr object, use dot notation.

The syntax to use dot notation looks like: xhr.someProperty.

6.
Save an empty anonymous arrow function to the onreadystatechange event handler of the xhr object. This function will not take in any parameters.

Inside the anonymous function’s code block, include the following code inside of its code block:

if (xhr.readyState === XMLHttpRequest.DONE) {
  renderRawResponse(xhr.response);
}
The renderRawResponse function can be viewed at public/helperFunctions.js.

Checkpoint 7 Passed

Hint
The syntax will look like:

xhr.onreadystatechange = () => {
  if (xhr.readyState === XMLHttpRequest.DONE) {
    renderRawResponse(xhr.response);
  }
}
7.
Below the anonymous function you just created, call the .open() method on xhr, and pass it 'POST' and url as respective arguments.

Checkpoint 8 Passed

Hint
The syntax will look something like:

xhr.open('HTTP Request Type', url)
8.
To access the Rebrandly API, we need a header with two key-value pairs. In the header, you must include values for 'Content-type' and an 'apikey'.

To set the header, we have to include the following code below our .open() method.

xhr.setRequestHeader('Content-type', 'application/json');
xhr.setRequestHeader('apikey', apiKey);
Checkpoint 9 Passed

Hint
Make sure you’re inside the code block for shortenUrl().

9.
On xhr, call the .send() method, and pass it data as an argument.

Checkpoint 10 Passed

Hint
Make sure you’re inside the code block for shortenUrl().

10.
Enter this URL into the input field, and click the shorten button in the web page.

https://medium.com/@codecademy/breaking-the-coding-language-barrier-bf24652c3c60
Notice the object that came back!

Now replace renderRawResponse(xhr.response) with renderResponse(xhr.response). Run the code.

Paste the URL again and click “Shorten”.

Isn’t it much cleaner?
