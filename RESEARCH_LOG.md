# Research Log: Eplanatory Gap Project

## [7/15/2026]

Applied for and got API key in less than 10 minutes

2nd Commit

Downloaded dotenv in venv

Created an .env to safely hold my key

Ensure .env was hidden from git

I made the program check if the user’s env has a valid API key.
- If so, continues
- If not, it defaults to checking if the IP is good via a simple request
- If the IP is good, continues

I had to make override=True for load_dotenv in order for the proper API to be accessed everytime.

Then I made a test for validating the key

I put in my actual key into .env and started trying the program.

I made it access specific fields and then switched to getattr because some papers didnt have abstracts. I put a cap on the characters for the abstract.

I had to switch to using AsyncSemanticScholar because of stalling in the background. 

I added await to statements to the two places where I search in Semantic Search (places #3 and #4)

Switched around order of if conditions for step 1 to prevent crash (put api_key is None first)

3rd Commit

## [7/14/2026]