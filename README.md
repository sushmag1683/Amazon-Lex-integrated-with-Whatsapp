# Amazon-Lex-integrated-with-Whatsapp

## Architecture of Project Amazon-Lex-integrated-with-Whatsapp

![image](https://github.com/sushmag1683/Amazon-Lex-integrated-with-Whatsapp/assets/116668536/dde9133b-9a3c-4482-a27f-f1467a6d3874)

Step-1 : 	Create a bot named as your wish, I created my Amazon Lex bot name as HotelBookRoom.

Step-2 : 	Create an intent named as Booking 

Step-3 : 	Create sample utteranes as below:
          'Book a hotel'
          'I want to make hotel reservations'
          'Book a {Nights} night stay in {Location}'

Step-4 :  Create slot values as below:
          Location     : AMAZON.City
          Nights       : AMAZON.Number
          CheckInDate  : AMAZON.Date
          RoomType     : AMAZON.Type

Step-5 :  Create confirmation and Fulfillment as below:
          Confirmation : Okay, I have you down for a 5 night stay in Hyderabad starting 2024- 
          04- 29. Shall I book the reservation?
          Fulfillment : Thank You

Step-6 : 	I have created a lambda function as HotelBookRoomLambda and deploy the lambda code


Step-7 : 	To check if there is an error in the code or the data is taken or not, we can check through CloudWatch Logs in which is in below of lambda, ’Monitor’.

Step-8 : 	Then Aliases should be created and I created Aliases as ‘BookingbotAlias’ of 
          'Version2'

Step-9 : 	 Create a Channel Integration by selecting the option using Twilio and created name as BookRoom

Step-10 : Open the website of twilio and create an account and sign up then main console will 
          be opened

Step-11 : Copy the Account SID and Auth Token and paste it in the channel integration which 
          has been created in aws console.

Step-12 :	Then we can see the Callback URL inside the channel integration and copy that.

Step-13 : Paste the Callback URL in sandbox settings of ‘When a message comes in and it should 
          be in ‘POST’ method.

Step-14 :	It give you a QR code code and number,save that number as our wish and they’ll give 
          a code which is used to start the conversation in whatsapp with the number.

Step-15 :	I saved the number as HotelBookRoom which is same as the Bot name and start the 
          conversation using the code which is displayed in twilio.

Step-16 :	I have sent a message as book hotel and it give me reply as ‘What city will you be 
          staying in?'

Step-17 : I have given as ‘Hyderabad’ and it sent reply as ‘What date you want to check in?'

Step-18 : I gave date as ’29-04-2024’ and it asked me as ‘How many Nights will you be staying?'

Step-19 :	I have given as ‘5’ and it asked me as ‘What type of room would you like 
          standard,deluxe or luxury?’

Step-20 :	I replied as luxury and it is asking confirmation of the details which I have been 
          given before as ‘Okay, I have you down for a 5 night stay in Hyderabad starting 
          2024-04-29. Shall I book the reservation?’

Step-21 : I gave reply as ‘yes’ and then it generated a message as ‘Thanks, I have placed your 
          reservation’
