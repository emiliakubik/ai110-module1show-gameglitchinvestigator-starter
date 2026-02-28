# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

  Game looks as expected when first opened but I ran into some bugs:
  1. Clicking return does not submit what I typed, even though it says it will, I have to click "Submit Guess" instead
  2. Everytime my guess is incorrect, the hint says "guess higher" even if my guess is too high or even out of range (1-100)
  3. The New Game button does not start a new game, I have to refresh page to start a new game

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I'm using Copilot for this project.
One correct suggestion AI made was that the game was suggesting "go higher" because the logic was backwards, I verified that by playing another round of the game and confirming that when I enter too low of a number, it suggested going lower, and when I entered too high of a number, it suggested going higher.
Something that was a little misleading was when we were on the testing phase, it was telling me all my tests were passing but the terminal very clearly said that 3 tests were still failing. It took a lot of rewording for it to get to the bottom of it, which was that the failing tests were not the tests we made, but ones that were already there prior. 

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

1. I decided a bug was really fixed when the pytest cases were passing, AND when I manually played the game and tried a bunch of different inputs and got the expected output.
2. One test I did was for the new game button, trying to restart the game before I took any attempts, then another try after I took half my attempts, another try when I had guessed it correctly, and finally another try when I had lost, when all successfully reset the game I knew it was fixed
3. AI helped me with writing and thinking up the pytest cases but the ones I did manually I did myself.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

I seemed to only notice the secret number changing when the game was restarted, after the previous secret number was either guessed or revealed. However, without session state, the secret number would be regenerating on every button click.
Streamlit is like a webpage that refreshes everytime you interact with it, the problem with that is that all variables reset anytime you click a button or type something. Session state is the only way you can make any variable survive the refresh.
The secret number was already stable using session state. 

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.


Learning the context variables trick (#file:app.py) is something I learned today I'll definitely be using again in the future.
One thing I'll be better about next time is creating a new chat for every issue, that definitely would've kept things cleaner today and easier for the AI to not get lost.
This project showed me how effecient but messy AI can be with generating code, and that it why it's such at wonderful tool but why we have to be one step ahead of it and always checking it before we just trust it and commit the work it's done for us. 