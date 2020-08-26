# Introduction to APIs

In this session, we are going to learn how to use Postman to interact with an API over HTTP.

## Installing Postman

Postman is a REST client, it allows us to interact with an API by building HTTP requests. This is very handy when we are building an API, or are learning how a new one works. One way to think of it is a web browser that doesn't render the web page.

[Download Postman Here](https://www.postman.com/downloads/)

You can find details of the interface [here](https://learning.postman.com/docs/getting-started/navigating-postman/). We recommend you also read the next page [sending your first request](https://learning.postman.com/docs/getting-started/sending-the-first-request/).

## Challenge
We will be using this [api](https://github.com/noops-challenge/fizzbot) to get used to sending `GET` and `POST` requests. The aim is to send a `GET` request to receive a question from the api, then send a `POST` request with an answer to the same url. If you answer correctly, you will receive the url to request the next question from.

When you're ready, send a `GET` request to `https://api.noopschallenge.com/fizzbot`. You should receive this response:

```json
{
  "message":"Thank you for your application to Noops Inc.\n\nOur automated fizzbot interview process will help us determine if you have what it takes to become a Noop.\n\nFor each question, you will GET the question and then give us the answer back to the same URL.\nYou will also find the URL for the next question in the nextQuestion parameter for each response.\n\nThe first question is at https://api.noopschallenge.com/fizzbot/questions/1.\n\nGood Luck\n",
  "nextQuestion":"/fizzbot/questions/1"
}
```

### JSON

The response will be in `JSON` (JavaScript Object Notation), this is a string which can be parsed into an object by most programming languages. It is syntactically similar to an object literal in JavaScript, with two key differences:

- Both the key and the value must be in double quotes
- The last value cannot have a comma after it 

In the response, you will see a property called `nextQuestion` with the route to send your next request to. Add this to the end of the base url of `https://api.noopschallenge.com/` and send you next get request.

## Sending your first POST request

Once you have the next question, we need to build a `POST` request to answer it. To do this you will need to:

-1 Set the request type next to the url bar as `POST`, the url should remain the same for answering the question.
-1 Click on the `body` tab, select the `raw` option. A dropdown menu will appear to the right, it will be set to `Text` by default. Set it to `JSON`
-1 We now need to write the request body, you may have guessed that it needs to be in `JSON`, it should look something like this:

```json
{
  "answer": "YOUR ANSWER HERE"
}
```

Once that's in place you should be good to send your first `POST` request.

## Next challenge

Okay, so this one is a bit more complicated. There's a few ways you could solve this. You could do it manually, or, you could dust off your old fizzbuzz kata and throw together a script to construct a string that will answer this question. 

When you're done, post it back to the url and see if you can get the next question. Be sure to let everybody else know when you manage to answer a question!