---
name: Feature request
about: For new workflows & change requests
title: ''
labels: feature request
assignees: ''

---
## Background, context, and business value

A clear and concise description of what the client wants and WHY. 

For example: [Insert use case here]

## The specific request, in as few words as possible

A clear and concise description of what you want to happen.  
Things to include as needed:
- The number of workflows needed to be created or updated 
- The function of each workflow including specific resources and operations
- Unique identifiers 
- Links to mapping specifications, data flow diagrams, sample input/output data, and any API documentation
- Links to the data model of target systems, if available


```md
Create a workflow in which OpenFn will: 
1. Get new rows from the PostgreSQL database every 1 hour
2. Clean & transform the data according to the specified mapping rules, and then 
3. Upsert cases in the Primero case management system via externalId `case_id`
(Note: 1 DB row will = 1 case record.)

See [links] below for the workflow diagrams, mapping specs, & Primero data model.
```

### Data Volumes & Limits
How many records do we think these jobs will need to process in each run? For example: 
```md
When you GET data from the DB, this may return up to 1000 records. 
There are no known Primero API limits for # of records, but there is API paging to consider.
```

## Input

### Credentials
Which credentials can be used to access the target system(s)? 
(Do NOT share credential secrets on this issue -> rather point to where it can be found).

### Data
Describe how the "input" for this workflow will be generated (e.g., webhook request, timer-based query to be sent). Either provide an example directly, link to a file, or describe how a query can be executed to extract data. 

Be sure to redact any sensitive data and to not paste here. 


## Workflow Steps

For each new Workflow, describe the number of steps needed and the high-level function of each step. Also include the trigger on platform and the adaptor needed for each step.
For existing steps, provide a link to the step itself in Github and the high-level changes needed to be made. _Provide the information below for _each_ step that is required._


### 1. Step Name  (e.g., `1. Get new DB rows`)

####  adaptor
E.g., `postgresql`

#### operation
E.g., Query (`SELECT * from table where created_at >= NOW()`)

#### output
List of new DB rows

## How to test 
Link to test suite and/or provide examples of input/output scenarios to validate the implementation. 

## Toggl


