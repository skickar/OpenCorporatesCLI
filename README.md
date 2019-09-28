# OpenCorporatesCLI

## Business search and fun with rate limiting

The goal of this project is to easily locate information on businesses, in particular filing documents.
This tool will search OpenCorporates to discover businesses with a matching name, then run a new search for each business found.
The new search will pull all filing documents for the jurisdiction the business is registered in.

Pros: 
* Easy access to filing documents
* Python CLI
* Looks badass & cool

Cons:
* RATE LIMITING FOR TOO MANY SEARCHES (can be solved with API key, but OpenCorporates has yet to issue me one)
* Data returned isn't fully formatted yet (the address portion)
* Can only search for business types, can't yet pull attached officers

### Install/run:
* git clone https://github.com/skickar/OpenCorporatesCLI.git
* pip3 install requests, json
* cd OpenCorporatesCLI
* python3 OCQuery.py


Sample output:

```skickar$ python3 OCQuery.py
Name of company to search?
>THERANOS, INC
Registered Name:  THERANOS, INC. founded on  2004-04-13
Business Number:  3789976
Inactive status:  None
Current status:  None
Jurisdiction:  us_de
Active from:  2004-04-13  to  None
Address:  None
Data Source:  Delaware Department of State: Division of Corporations at link  http://www.corp.delaware.gov/
Opencorporates URL:  https://opencorporates.com/companies/us_de/3789976
END OF RESULT

Registered Name:  THERANOS, INC. founded on  2004-05-03
Business Number:  C2651481
Inactive status:  True
Current status:  Surrender
Jurisdiction:  us_ca
Active from:  2004-05-03  to  None
Address:  {'street_address': '1701 PAGE MILL ROAD\nPALO ALTO CA 94304', 'locality': None, 'region': None, 'postal_code': None, 'country': 'United States'}
Data Source:  California Secretary of State at link  https://businessfilings.sos.ca.gov/frmDetail.asp?CorpID=02651481
Opencorporates URL:  https://opencorporates.com/companies/us_ca/C2651481
Filing:  SURRENDER
Link to filing:  https://businesssearch.sos.ca.gov/Document/RetrievePDF?Id=02651481-25452925
Date filed:  2018-12-31
Filing:  AGENT RESIGNED
Link to filing:  https://businesssearch.sos.ca.gov/Document/RetrievePDF?Id=02651481-25173496
Date filed:  2018-11-09
Filing:  SI-NO CHANGE
Link to filing:  https://businesssearch.sos.ca.gov/Document/RetrievePDF?Id=02651481-22838699
Date filed:  2017-09-01
Filing:  SI-COMPLETE
Link to filing:  https://businesssearch.sos.ca.gov/Document/RetrievePDF?Id=02651481-19688745
Date filed:  2015-08-31
Filing:  AMENDED REGISTRATION
Link to filing:  https://businesssearch.sos.ca.gov/Document/RetrievePDF?Id=02651481-6312799
Date filed:  2005-01-12
Filing:  AMENDED REGISTRATION
Link to filing:  None
Date filed:  2005-01-12
Filing:  REGISTRATION
Link to filing:  https://businesssearch.sos.ca.gov/Document/RetrievePDF?Id=02651481-5605113
Date filed:  2004-05-03
END OF RESULT

Registered Name:  THERANOS, INC. founded on  2012-05-01
Business Number:  F12000001870
Inactive status:  True
Current status:  Inactive
Jurisdiction:  us_fl
Active from:  2012-05-01  to  None
Address:  None
Data Source:  Florida Department of State Division of Corporations at link  http://www.sunbiz.org
Opencorporates URL:  https://opencorporates.com/companies/us_fl/F12000001870
END OF RESULT

Registered Name:  Theranos, Inc. founded on  2015-05-21
Business Number:  4357259
Inactive status:  False
Current status:  Active
Jurisdiction:  us_pa
Active from:  2015-05-21  to  None
Address:  {'street_address': '1250 Camp Hill Bypass Camp Hill PA 17011 Cumberland', 'locality': None, 'region': None, 'postal_code': None, 'country': 'United States'}
Data Source:  Pennsylvania Department of State at link  https://www.corporations.pa.gov/search/corpsearch
Opencorporates URL:  https://opencorporates.com/companies/us_pa/4357259
Filing:  CERTIFICATE OF AUTHORITY 1
Link to filing:  None
Date filed:  2015-05-21
Filing:  Creation Filing 1
Link to filing:  None
Date filed:  2015-05-21
END OF RESULT```

