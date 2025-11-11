---
title: Tutorial V.I - Programming with AI
subtitle: 'Programming: Everyday Decision-Making Algorithms'
author: Dr. Tobias Vlćek
format:
  revealjs:
    footer: ' {{< meta title >}} | {{< meta author >}} | [Home](tut_05_01_llm.qmd)'
    output-file: tut_05_01_presentation.html
---


# <span class="flow">Using AI</span>

## Using AI to generate code

-   Coding by hand is <span class="highlight">not the only way to generate code</span>
-   Most likely, a lot of you have already used **ChatGPT**

. . .

<center>
<iframe src="https://giphy.com/embed/0lGd2OXXHe4tFhb7Wh" width="400" height="400" style frameBorder="0" class="giphy-embed" allowFullScreen>
</iframe>
</p>
</center>

# <span class="flow">Large Language Models</span>

## 

How do

Large Language

Models work?

<span class="white">Photo by <a href="https://unsplash.com/@tvick">Taylor Vick</a> on Unsplash</span>

## Large Language Models (LLMs)

-   Think of them like <span class="highlight">advanced pattern recognition systems</span>
-   They have "read" **massive amounts of text**
-   Books, websites, articles, code, and more
-   Text is broken into **tokens**, parts of words or punctuation
-   Based on patterns, they can **generate new text**

## Training LLMs

-   Imagine learning a language by <span class="highlight">reading millions of books</span>
-   Learns patterns in **how words and ideas connect** via tokens
-   Interconnected nodes with **weights representing patterns**
-   During training, these **weights are adjusted**
-   Once trained, **applying** them takes much less ressources

## Pattern Recognition

-   <span class="highlight">Not like a search engine!</span>
-   When asked, it looks for **relevant patterns** it learned
-   Like having a **huge library** in its "memory" to draw from
-   It can find **patterns between concepts** and your question
-   Knows only limited text at once (**context window**)

## Probability based responses

-   After each token, it predicts <span class="highlight">"what should come next?"</span>
-   Like a advanced **word prediction** on your phone
-   Chooses the **most likely next token** based on training
-   <span class="highlight">Uses randomness to **generate different responses**</span>
-   <span class="highlight">But can't actually "think" or "understand" like humans</span>

## Limitations

-   **No true understanding** of cause and effect
-   Sometimes **makes mistakes or "hallucinates"**
-   Mostly only knows what it **was trained on**
-   Can **reflect biases** present in training data
-   No emotional understanding (but <span class="highlight">can simulate responses!</span>)

## Impact on Jobs

-   <span class="question">Question</span>: What do you think about their impact on jobs?
-   <span class="question">Question</span>: What are the implications for us?
-   <span class="question">Question</span>: Can we use them to our advantage?

# <span class="flow">Code Generation Tools</span>

## (Current) Choices for Programmers

-   [Github Copilot](https://github.com/features/copilot): Integrated into VS Code by Microsoft
-   [Cursor](https://www.cursor.com/): Fork of VS Code with AI assistance built in
-   [Aider](https://aider.chat): Chat interface for AI to write code in the terminal

. . .

> **Tip**
>
> Currently, [Cursor](https://www.cursor.com/) is my favorite one. But this might change in the future, as there is a lot of competition in this space.

## Installing Cursor

-   Go to [Cursor](https://www.cursor.com/)
-   **Download** and **install** Cursor
-   You will need to create an account
-   Some free usage per month, after that you need to pay
-   For us, the **free plan should be more than enough**

## Using Cursor

-   Open the folder with your tutorial files
-   Instead of notebooks, we will use `.py` files
-   Create a new `.py` file
-   Press `Ctrl + L` to open the chat

## Asking for help

<span class="task">Task</span>: Paste the following prompt in to the chat:

*Can you please write me a small random number guessing game in python? It should work for one player in the terminal. The player should guess a number between 1-10 and get hints about whether his guess was too large or too small. After 3 tries, end the game if he didn't succeed with a nice message.*

. . .

<span class="highlight">Copy the generated code and paste it into your file.</span>

## More on Cursor

-   While working with Cursor, it will **suggest** you code changes
-   You can **accept** or **reject** them
-   The rest you will **learn by doing!**

. . .

> **Note**
>
> **And that's it for the introduction to AI!**  
> You now have the basic knowledge to start working with <span class="highlight">AI!</span>.
