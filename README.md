Barakah TechLabs Internship - Task 1
Topic: Zero-Shot vs Few-Shot Prompting

For my first task, I tested how AI classifies 10 customer support messages into 4 categories (Billing, Tech Issue, Account Access, and Feature Request). I wanted to see the accuracy difference between a normal prompt (Zero-Shot) and a prompt with examples (Few-Shot).


--- Prompt 1: Zero-Shot Prompt ---

Hey, I have 10 customer messages below. Can you classify each one into one of these 4 categories?
Categories: Billing, Tech Issue, Account Access, Feature Request.
Just give me the number and the category name, nothing else.

1. "I updated the app and now my screen goes black every time I open my invoice page."
2. "Why was I charged $49 twice this month? Fix this before I call my bank."
3. "It would be great if we could export our monthly billing history as a PDF."
4. "I changed my phone number and now I'm not getting the 2FA code to log in."
5. "The checkout button is completely frozen when I try to upgrade my plan."
6. "Can you add a dark mode? My eyes hurt using the dashboard at night."
7. "I cancelled my subscription 3 days ago, why is my card still being billed?"
8. "My team member left the company, how do I revoke his admin login immediately?"
9. "I wish there was a way to split payments between two credit cards."
10. "Every time I click 'Reset Password', the page throws a 500 Internal Server Error."


--- Prompt 2: Few-Shot Prompt ---

Hey, I need you to classify 10 customer messages into one of these 4 categories: Billing, Tech Issue, Account Access, or Feature Request.

Sometimes the messages are tricky because they mention billing or login words, so look at what the actual problem is. Here are 4 examples of how I want you to do it:

Example 1: "The 'Pay Now' button gives a 404 error when I click it." -> Tech Issue (404 error is a bug, even on the payment page)
Example 2: "Can you guys add PayPal as a payment option?" -> Feature Request (asking for a new feature, not a billing issue)
Example 3: "I forgot my security question and can't get into my account." -> Account Access
Example 4: "You charged me for the Pro plan instead of Basic." -> Billing

Now follow the same logic for these 10 messages and just give me the number and category:

1. "I updated the app and now my screen goes black every time I open my invoice page."
2. "Why was I charged $49 twice this month? Fix this before I call my bank."
3. "It would be great if we could export our monthly billing history as a PDF."
4. "I changed my phone number and now I'm not getting the 2FA code to log in."
5. "The checkout button is completely frozen when I try to upgrade my plan."
6. "Can you add a dark mode? My eyes hurt using the dashboard at night."
7. "I cancelled my subscription 3 days ago, why is my card still being billed?"
8. "My team member left the company, how do I revoke his admin login immediately?"
9. "I wish there was a way to split payments between two credit cards."
10. "Every time I click 'Reset Password', the page throws a 500 Internal Server Error."


--- My Results & Accuracy ---

Correct Answers:
1. Tech Issue
2. Billing
3. Feature Request
4. Account Access
5. Tech Issue
6. Feature Request
7. Billing
8. Account Access
9. Feature Request
10. Tech Issue

Zero-Shot Result: 6/10 correct (60% Accuracy)
In zero-shot, the AI got confused on message 1, 3, 9, and 10 because it just looked at words like "invoice", "payments", and "password" instead of understanding the real problem.

Few-Shot Result: 10/10 correct (100% Accuracy)
After I added the 4 examples, the AI understood the difference between an actual billing problem and a tech bug happening on a billing page. It got all 10 right.

(I have also uploaded the output screenshots in this repo).
