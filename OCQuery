## OpenCorporates CLI search with lots of rate limiting
## Requires no API key but may be rate limited after several searches
## If you have a VPN, turn it on and change regions before using to avoid your primary IP being limited

import requests, json

companySearch = input("Name of company to search?\n>")
data = (requests.get("https://api.opencorporates.com/v0.4/companies/search?q={}".format(companySearch))).json();
for i in range(len(data['results']['companies'])):
    print("Registered Name: ",data['results']['companies'][i]['company']['name'], "founded on ",data['results']['companies'][i]['company']['incorporation_date'] )
    print("Business Number: ",data['results']['companies'][i]['company']['company_number'])
    print("Inactive status: ",data['results']['companies'][i]['company']['inactive'])
    print("Current status: ",data['results']['companies'][i]['company']['current_status'])
    print("Jurisdiction: ",data['results']['companies'][i]['company']['jurisdiction_code'])
    print("Active from: ",data['results']['companies'][i]['company']['incorporation_date'], " to ",data['results']['companies'][i]['company']['dissolution_date'])
    print("Address: ",data['results']['companies'][i]['company']['registered_address'])
    print("Data Source: ", data['results']['companies'][i]['company']['source']['publisher'], "at link ",data['results']['companies'][i]['company']['source']['url'])
    print("Opencorporates URL: ", data['results']['companies'][i]['company']['opencorporates_url'])
    filings = (requests.get("https://api.opencorporates.com/v0.4/companies/{}/{}/filings".format(data['results']['companies'][i]['company']['jurisdiction_code'],data['results']['companies'][i]['company']['company_number']))).json();
    for i in range(len(filings['results']['filings'])):
        print("Filing: ", filings['results']['filings'][i]['filing']['title'])
        print("Link to filing: ", filings['results']['filings'][i]['filing']['url'])
        print("Date filed: ", filings['results']['filings'][i]['filing']['date'])

    print("END OF RESULT\n")
