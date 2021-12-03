---
name: Feature request
about: For requesting changes to jobs
title: ''
labels: enhancement
assignees: ''

---

## Background, context, and business value

A clear and concise description of what the client wants and WHY.

For example: [Insert use case here]

## The specific request, in as few words as possible

A clear and concise description of what you want to happen.  
Things to include as needed:
- The number of jobs needed to be created or updated 
- The function of each job including specific resources and operations
- Unqiue identifiers 
- Links to mapping specifications, data flow diagrams, sample input/output data, and any API documentation


```md
Create jobs 1 &2 in which OpenFn gets cases from Primero and gets the case and services, maps the Primero extract and upserts to Progres

1. Get referral data: GET /api/v2/cases -- where service_implementing_agency='UNHCR'
   This should return: https://github.com/OpenFn/primero-progres/blob/master/sampleData/primero_sample_state.json
2. Map Primero response to DTP/Progres interface. The field progres_primeroid will be the primary uid used by DTP.
3. Upload referrals to DTP/Progres: POST https://antirrio.azure-api.net/primero-uat/ReceiveIncomingReferral
```


## state.json

Either provide state directly, or link to a file. If sensitive information
should be in state, redact it and provide instructions for where it can be
found.


```json
{
  "configuration": ["SEE LAST PASS: 'client cred'"],
  "data": { LINK TO STATE },
  "cursor": "2020-01-19 00:00:00"
}
```


## expression.js

**For new jobs**, describe the number of jobs needed and the high-level function of each job.  Also include the trigger on platform and the adaptor needed for each job.   
**For existing jobs**, provide a link to the job itself in Github and the high-level changes needed to be made.

```md
3 jobs...

Job 1
Adaptor: Primero
Trigger: Cron - daily at 12:00 AM
Function: GET cases from Primero
Output: Link to sample output

Job 2
Adaptor: HTTPS
Trigger: Flow - Job 1 
Function: Map Primero response to DTP/Progres and upload referrals to DTP/Progres
Output: Link to sample output

Job 3
Adaptor: Primero
Trigger: Message filter - `{form: "form-name"}`
Function: Upsert Primero with decision status
Output: Link to sample output

```
