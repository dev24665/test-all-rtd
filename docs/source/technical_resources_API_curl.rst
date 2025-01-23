Performing requests with curl
--------------
A GraphQL request is a standard HTTPS POST request, with a JSON-encoded body containing a "query" key, and optionally a "variables" key. For example, the following curl command returns the case submitter id project submitter id disease typeproperties for a queried case:
                         
     curl https://pdc.cancer.gov/graphql      -H "Content-Type: application/json"      -d '{"query": "{ case(case_submitter_id: "01BR001" acceptDUA: true)      { case_submitter_id project_submitter_id disease_type }}"}'

     {
     "data": {
     "case": {
    "case_submitter_id": "01BR001",
    "project_submitter_id": "CPTAC-2",
    "disease_type": "Breast Invasive Carcinoma"
    }
    }
   }
  
