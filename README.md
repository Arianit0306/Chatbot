# THE CHATBOT

I made a custom chatbot using openai's API key. You can customixe this but it costs money. You can decide which mood the chatbot is in for instance sad, happy. I have made this myself. 


# chatbot.py

import openai

openai_key = "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"

completion = openai.ChatCompletion.create(model="gpt-3.5-turbo", messages=[{"role": "user", "content": "Give me 3 ideas for apps I could build with openai apis "}])
print(completion.choices[0].message.content)


# chatbot assistant.py

import openai

openai.api_key = "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"

messages = []
system_msg = input("What type of chatbot would you like to have?\n")
messages.append({"role": "system", "content": system_msg})

print("Your assistant is ready!")
while True:
    user_input = input()
    messages.append({"role": "user", "content": user_input})
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=messages
    )
    reply = response['choices'][0]['message']['content']
    messages.append({"role": "assistant", "content": reply})
    print("\n" + reply + "\n")


# API
https://platform.openai.com/account/api-keys


