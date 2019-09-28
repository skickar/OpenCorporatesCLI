# OpenCorporatesCLI

## Business search and fun with rate limiting

The goal of this project is to easily locate information on businesses, in particular filing documents.
This tool will search OpenCorporates to discover businesses with a matching name, then run a new search for each business found.
The new search will pull all filing documents for the jurisdiction the business is registered in.

Pros: 
Easy access to filing documents
Python CLI
Looks badass & cool

Cons:
RATE LIMITING FOR TOO MANY SEARCHES (can be solved with API key, but OpenCorporates has yet to issue me one)
Data returned isn't fully formatted yet (the address portion)
Can only search for business types, can't yet pull attached officers

Install/run:
git clone https://github.com/skickar/OpenCorporatesCLI.git
pip3 install requests, json
cd OpenCorporatesCLI
python3 OCQuery.py

