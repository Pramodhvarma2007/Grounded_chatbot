# Grounded Chatbot (FoodExpress Support)

A simple customer support chatbot built in Google Colab using the Google Gemini API. The chatbot is "grounded" in a fixed set of FoodExpress support information, so it answers only from that information. If a question is outside its knowledge (for example, the weather), it politely says it doesn't have enough information instead of making up an answer.

**Author:** A. Pramodh Varma
**GitHub:** [Pramodhvarma2007](https://github.com/Pramodhvarma2007)

---

## Features

- Acts as a **FoodExpress Support** assistant
- Answers questions about order tracking, cancellation and delivery delays
- Stays grounded: refuses to answer questions outside the provided information
- Runs as a continuous chat loop in the notebook
- Type `bye` or `quit` to exit

## Tech Stack

- Python
- Google Colab / Jupyter Notebook
- Google Gemini API (`google-genai` library)

## Installation

Run this in the first cell of the notebook:

```python
!pip install -q -U google-genai
```

## Setup

1. Get a free API key from [Google AI Studio](https://aistudio.google.com/).
2. Add it to the notebook as `GEMINI_API_KEY`. In Colab, use **Secrets** (the key icon on the left sidebar).
3. Do **not** paste your API key directly into the code or upload it to GitHub.

## How to Run

1. Open `Grounded_chatbot.ipynb` in Google Colab.
2. Run the install cell.
3. Run all cells (**Runtime → Run all**).
4. Type your question when you see `Ask your Question:`.
5. Type `bye` or `quit` to end the chat.

## How It Works

1. The chatbot is given instructions and support information about FoodExpress.
2. The user's question is sent to Gemini through a chat session (`chat.send_message`).
3. The model answers using only the given information.
4. If the answer isn't in that information, it replies that it doesn't have enough information.

## Example Run

```
Hi! I am FoodExpress Support.
Type 'bye' or 'quit' to exit.

Ask your Question: How can I track my order?
FoodExpress Support: To track your order, open "My Orders" and select your
current order to check the status and delivery information.

Ask your Question: Can I cancel my order?
FoodExpress Support: Yes, you can cancel your order if the restaurant has
not started preparing it.

Ask your Question: My food is late
FoodExpress Support: Check the estimated delivery time in My Orders. If the
order is significantly delayed, contact customer support through the Help
section.

Ask your Question: What is the weather today?
FoodExpress Support: I'm sorry, I don't have enough information to answer
that question.
```

The last question shows the grounding in action: the weather is not part of the FoodExpress information, so the bot declines instead of guessing.

## Project Structure

```
grounded-chatbot/
├── Grounded_chatbot.ipynb   # Main notebook
└── README.md                # Project description
```

## Future Improvements

- Add more support topics (refunds, payments, offers)
- Load the support information from a file or database
- Build a web interface for the chatbot

## License

This project is for educational purposes.
