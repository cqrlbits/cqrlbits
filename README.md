**TEXT SUMMARIZER**

Our product—Text Summarizer—provides deep learning summary using three machine learning models: ‘T5-FLAN’, ‘T5-XL’, and ‘Pegasus’.

![image](https://user-images.githubusercontent.com/88929533/204211848-a3236d6b-76fb-4107-b39a-45689ccb5b07.png)

POST an input JSON to the API endpoint:

http://cqrl.ai:8080/summarizer/api

A command-line curl example is provided below:

**_Input_**

$ _curl -X POST -H "Content-Type: application/json" -d '{"name": "adam", "email": "adam_name@email.com", "text": "The tower is 324 meters (1,063 ft) tall, about the same height as an 81-storey building, and the tallest structure in Paris. Its base is square, measuring 125 meters (410 ft) on each side. During its construction, the Eiffel Tower surpassed the Washington Monument to become the tallest man-made structure in the world, a title it held for 41 years until the Chrysler Building in New York City was finished in 1930. It was the first structure to reach a height of 300 meters. Due to the addition of a broadcasting aerial at the top of the tower in 1957, it is now taller than the Chrysler Building by 5.2 meters (17 ft). Excluding transmitters, the Eiffel Tower is the second tallest free-standing structure in France after the Millau Viaduct.","min":10, "max":20}' https://cqrl.ai:8080/api

Input JSON "text", "max" and "min" are mandatory fields. 
The output will provide an additional field "summary". Any other field in the input JSON will be retained and returned in the output JSON (see example below).

In the input JSON, an additional field “key” needs to be included for executing the summarizer API. This key will be provided on demand.
_
**_Output_**

{
  _"name": "adam",
  "email": "adam_name@email.com",
  "text": "The tower is 324 meters (1,063 ft) tall, about the same height as an 81-storey building, and the tallest structure in Paris. Its base is square, measuring 125 meters (410 ft) on each side. During its construction, the Eiffel Tower surpassed the Washington Monument to become the tallest man-made structure in the world, a title it held for 41 years until the Chrysler Building in New York City was finished in 1930. It was the first structure to reach a height of 300 meters. Due to the addition of a broadcasting aerial at the top of the tower in 1957, it is now taller than the Chrysler Building by 5.2 meters (17 ft). Excluding transmitters, the Eiffel Tower is the second tallest free-standing structure in France after the Millau Viaduct.",
  "min": 10,
  "max": 20,
  "summary": "The Eiffel Tower is the tallest structure in Paris."
  "model": "flan-t5-xl"_
}
![image](https://user-images.githubusercontent.com/88929533/204211158-d6c59647-bb91-41e0-8617-d355a4e4a65f.png)
