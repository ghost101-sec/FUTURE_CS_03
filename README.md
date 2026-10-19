# FUTURE_CS_03: API Security Risk Analysis

**Internship:** Future Interns, Cyber Security Track
**Task:** 3, API Security Risk Analysis
**Author:** Edwin Baiju

## Overview
This project reviews a public demo API for common API security problems: data exposure, authentication and access control, rate limiting and input validation. Each issue is rated by risk, explained in simple business language, and given a fix.

## Target
DummyJSON (`https://dummyjson.com`), a public demo API made for practice, with fake data. Only light, normal requests were sent. No attacks, floods or stress tests were run.

## What's Inside
- `API_Security_Risk_Analysis_Report.pdf`: the full report
- `req2_users.png`: user records returned without logging in
- `rate_limit_test.png`: 20 requests, all 200 OK
- `input_validation.png`: unusual login input handled safely

## Summary of Findings
| Risk | Count |
|---|---|
| High | 1 |
| Medium | 1 |
| Low | 2 |

**Overall risk rating: High (in a real system)**

## Key Findings
- User records readable without a token (excessive data exposure, weak access control)
- No visible rate limiting (20 requests, all 200 OK)
- Content-Security-Policy header not set
- Verbose responses returning more fields than needed

## Good Practices Observed
- Protected endpoint rejected requests with no token (401)
- No open CORS policy
- Empty and unusual login input rejected safely (400)

## Tools Used
Postman, browser

## Limitations
Only light testing was done on a demo API, so deeper flaws may exist that this review did not find.
