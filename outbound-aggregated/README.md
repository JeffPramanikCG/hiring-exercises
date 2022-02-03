# Aggregated Outbound calls (Ruby Lang)

Given a JSON-based dataset `cg-dev-test-feb-2.json` (taken from one PostgreSQL table).
JSON dataset has `created_at` timestamp values from 2021-11-12 to 2021-11-26.

## Task

Create a Ruby class/classes based on https://github.com/AaronLasseigne/active_interaction
which returns a `Hash` with keys sorted by `created_at` ascending order.

Hash structure:
- key: timestamp's day as a string `created_at`
- value: array of hashes (records grouped by the same day) with the following keys:
  - `client_id`
  - `outbound` - number of Oubound records for ther same `client_id` where "entryable_type": `PhoneCall::Outbound`
  - `admin` - boolean, true if `admin_id` is not null

## Example output:

```
{
    "2021-11-12" => [
        {
            client_id: 611,
            outbound: 5,
            admin: false
        },
        {
            ...
        },
        ...
    ]
    ...    
    "2021-11-26" => [
        ...
    ]
}
```

## Guidelines

* Use Ruby lang
* app should be runnable via `$>ruby task.rb`
* Do not fork this repo, archive your solution and send back to interviewer contact email
* Feel free to ask for any clarification
