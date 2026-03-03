# Lab-4-CSCI-2910
API project that involves live exchange rate of currency's. 


1. Handling Uppercase vs. Lowercase: I noticed that if I typed "eur" instead of "EUR," the API wouldn't recognize the code. I fixed this by adding .upper().strip() to the input line so the program automatically fixes the casing for the user.

2. Empty Input Crashes: There was an issue where if I accidentally hit "Enter" without typing anything, the program would try to look up a blank string and error out. I added validation to make sure the input isn't empty before the dictionary lookup starts.

3. Math with "Dirty" Input: I realized that if a user typed a dollar sign ($) or a comma in the amount field, Python couldn't convert it to a float. I had to add a try/except block specifically for the amount input to tell the user to only use numbers.

4. Pydantic Default Values: Initially, my Pydantic model required a user_amount every time, which made testing one-off rates annoying. I set a default value of 1.0 in the Currency class so I can see the base exchange rate even if I don't provide a specific amount.

5. API Response Latency: Sometimes the connection would hang if the server was slow. While I couldn't speed up the internet, I added a "Connecting..." print statement at the start so the user knows the program hasn't frozen while it's waiting to retrieve the data.
