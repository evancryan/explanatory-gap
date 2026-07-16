# Research Log: Eplanatory Gap Project

## Current Methodology

I will use two forms of data extraction. The first method will be based on phenomenas that present the explanatory gap. I will search for certain key words and tags to find phenomenas. I do not at all want to choose manually between more subjective or objective essays. I just want to see what conversations are being had on the subject. This first method of extraction will be split in half: I will query for major phenomenas and minor phenomenas. The second method will be based on citations.

## [7/16/2026]

I started with building the first method. I would specifically look into a major phenomena of the explanatory gap: musical frisson.

I created a list of terms and a list of search queries. I used a loop which had AsyncSemanticSearch search for each query, and then give back the 1000 results. But there would be a high amount of duplicates as the bucket filled up with results from these similar queries. So, I made the program only add to the bucket unique papaers. I was happy to receive consistently 5000-6000 unique papers which I would then filter. After I would apply filtering, I was hoping for a few hundred papers to be kept.

Initially I was just using one list of terms for filtering. This was yielding me around 180 results. However, I switched to two lists of terms, topic-related and neuroscience related, to be more precise. This first application of the dual-filter cut down the results to only 33 papers. After refining both lists with numerous more terms, I managed to keep 74 papers. This shows there was likely a lot of neuroscientific terms I was missing out on at first. After adding more terms and revising some of the queries, I got to keep 72 papers. One more expansion of terms left me with 82 papers. 

I decided to make two frequency dictionaries to find out which terms were being found the most from the dual terms lists. So, I would collect found terms in a list. At first, I made the program add each term found before papers were erased. But this was leaving phantom data in my frequency dictionaries. So, I made it add each term found in a paper to a temp list, and then only added those temp terms if the papers were kept. Then, I collected the found terms lists into dictionaries and printed the results.

After all this, I had my accurate frequencies. But I found certain words to be far too broad when the point of the Neuro Terms list was to identify the specific neuroscience genre. Interdisciplinary words like "brain" would likely already be covered if someone was talking about an fMRI scan. These common words were:
- physiologic: 36
- reward: 33
- brain: 30
- scan: 4

I dropped physiologic and merged brain / scan. Then, I changed reward to reward circuit, reward system and reward path. After doing so, I was left with 65 papers. That means that I eliminated 17 papers that might have been talking about the psychological effects of brain frills, not the pure neuroscience. Here's some noticeable results:
- reward system: 5
- reward circuit: 3
- brain scan: 0

4th Commit

## [7/15/2026]

Woke up and found I was still IP blocked

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

0th Commit (Initial Commit)

Downloaded pandas, requests, semanticscholar, and ipykernel into my virtual environment.

Had to manually add my venv to be rezognized for usage in VScode

Wrote code and encountered error/status code 429 using requests

Stopped using requests and switched to semantic scholar. Accidentally tried printing 17000 papers in a loop.

Ran loop again and found I was IP blocked for too many requests.

Added a checker to see when my IP was blocked or not. Got deadlocked in backlogging process between python and Semantic Scholar.

Installed and implemented nest_asyncio to process deadlock. Found I was still blocked.

1st Commit?
