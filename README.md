## POST Request for SH 

URL = 'http:LOCALHOST:PORT/retrieve_context/'

## Input params takes in the following three params with data types mentioned:
/retrieve_context

	- user_query: str = "What is the total amount in the Bill?"
	- chat_history: Optional[Union[List[Dict[str, str]], None]] = []
	- file: Optional[bytes]

## Output params is a json response with the key "text" and "source":
/Response

	- text: str = "This is the relevant text"
 	- source: List[str] = ["https://en.wikipedia.org/wiki/G42_(company)", "https://core42.ai/"]

## Example of chat history with two turns of conversation
```python
chat_history = [
    {"role": "user", "message": "Can you please tell me about the sports football in brief."},
    {"role": "assistant", "message": "Sure! Football, also known as soccer, is a popular sport played all around the world. It involves two teams of 11 players each trying to score goals by kicking the ball into their opponent's net. The game is played on a rectangular field with goalposts at either end. The team that scores more goals during the match wins. Football can be quite physical, but it's mainly a game of skill, strategy, and teamwork. It has a huge global following and is considered the most popular sport in many countries."},
    {"role": "user", "message": "What are some of the major leagues for it?"},
    {"role": "assistant", "message": "Some of the major leagues for football include the English Premier League, La Liga (Spain), German Bundesliga, Serie A (Italy), and Ligue 1 (France). These leagues are home to some of the top football clubs in the world and attract a lot of attention from fans worldwide."}
]
```

## Curl Command format

```bash
curl -X 'POST' \
  'http:<IP>:<PORT>/retrieve_context/' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "user_query": "Hi there!",
  "chat_history": [],
  "upload_file": b"some bytes",}'
```

## Other requirements:

    - File formats supported?
    - Max file size supported?
    - Average latency of end to end request as a function of file upload size 
    - Average latency of end to end request as a function of file input query + chat history bucketed to different file sizes
    - Does the PDF need to be readbale or do you have inbuilt OCR for non readable PDFs
    
 	
