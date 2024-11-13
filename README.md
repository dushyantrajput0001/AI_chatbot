Table of Contents
Deploy Lex bot and Alexa backend function using Java
JSON Document
Different platforms
Lex
Twilio/SMS
Facebook
Slack
Alexa
Web
Mobile
Logging using Amazon CloudWatch
Monitoring using AWS X-Ray
How to talk to the chatbot?
This repository explains how to create a Star Wars chatbot using Amazon Lex and Java.

logo
The users can interact with this chatbot using the following means:

Voice (Alexa, Phone/Call)

Text (Phone/SMS, Facebook Messenger, Slack)

Here are the key components of architecture:

architecture
Deploy Lex bot and Alexa backend function using Java

You need to install org.sample.aws.lex:lex-java:0.2 dependency as explained at https://github.com/arun-gupta/lex-java#install-jar-locally before building this project.

mvn -f starwars-chatbot/pom.xml clean package install
ARN for Alexa function: aws lambda get-function --function-name StarWarsChatbot --region us-east-1 | jq .Configuration.FunctionArn

Note
Getting Started with Alexa skill using Java is explained at https://github.com/arun-gupta/alexa-skill-java.
JSON Document

Data is loaded as JSON documents in DynamoDB. Here is a sample JSON document:

{
  "dead": true,
  "force-sensitive": true,
  "force-side": "light",
  "id": 1,
  "lightsaber": "green",
  "planet": "Dagobah",
  "quotes": [
    "When nine hundred years old you reach, look as good you will not.",
    "Truly wonderful, the mind of a child is",
    "A Jedi uses the Force for knowledge and defense, never for attack",
    "That is why you fail.",
    "Adventure. Excitement. A Jedi craves not these things.",
    "Judge me by my size, do you?",
    "Fear is the path to the dark side",
    "Wars not make one great",
    "Do, or do not. There is no try",
    "Size matters not",
    "The dark side clouds everything",
    "Impossible to see the future is",
    "Clear your mind must be",
    "Much to learn you still have ... my old padawan"
  ],
  "weapon": "lightsaber",
  "whoami": "Yoda"
}
Create Global Secondary Index on whoami

Different platforms

Lex

http://docs.aws.amazon.com/lex/latest/dg/using-lambda.html

lexbot
Twilio/SMS

Send a message to 408-913-9827 as shown below:

sms
Details: https://docs.aws.amazon.com/lex/latest/dg/twilio-bot-association.html

Facebook

Like https://www.facebook.com/Star-Wars-Chatbot-124902658243108/

From http://messenger.com, send a message to this page as shown below:

facebook
Details: http://docs.aws.amazon.com/lex/latest/dg/fb-bot-association.html

Slack

Get yourself invited: https://join.slack.com/t/starwarschatbot/shared_invite/MjM4OTU2MTEwMTE0LTE1MDUwOTgzMzItYzZmMjFhYTNiNA

DM with the app star_wars_chatbot and ask questions as shown below:

slack
Details: https://docs.aws.amazon.com/lex/latest/dg/slack-bot-association.html

Alexa

Test using http://echosim.io or Alexa

Web

TODO

Mobile

TODO

Logging using Amazon CloudWatch

Monitoring using AWS X-Ray

TODO

How to talk to the chatbot?
