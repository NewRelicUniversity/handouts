Lab: Explore your data
---
`SHOW EVENT TYPES`

`SELECT keyset() FROM Transaction`

`SELECT count(*) FROM Transaction`

`SELECT count(*) FROM Transaction FACET appName`

---
FACET Linking
---
`SELECT count(*) FROM Transaction FACET appName LIMIT MAX`

---
Patterns
---
`SELECT uniqueCount(session) FROM PageView WHERE appName = 'Frontend' SINCE 5 minutes ago`

`SELECT uniqueCount(session) FROM PageView WHERE appName = 'Frontend' SINCE 1 day ago TIMESERIES`

`SELECT uniqueCount(session) FROM PageView WHERE appName = 'Frontend' SINCE 1 week ago TIMESERIES`

---
Lab: Try out time spans and TIMESERIES
---
`SELECT count(*) FROM Transaction WHERE httpResponseCode = '500' SINCE __________ UNTIL ___________`

`SELECT average(pageRenderingDuration) FROM PageView SINCE 12 hours ago`

- TIMESERIES
- TIMESERIES 5 minutes
- TIMESERIES MAX

---
Adding your own values and thresholds to charts
---
`SELECT average(duration), 0.1 as 'threshold', 0.05 as 'warning' FROM Transaction SINCE 1 day ago TIMESERIES`

---
Compare performance over time `SINCE...COMPARE WITH` 
---
`SELECT uniqueCount(session) FROM PageView WHERE appName = 'Frontend' SINCE 1 week ago COMPARE WITH 1 week ago TIMESERIES 1 hour`

---
Compare data sets with multi-FACET and FACET CASES
---
**Multi-FACET**

`SELECT average(duration) from PageView facet pageUrl, countryCode, city`

**FACET CASES (using labels)**

`SELECT count(*) FROM Transaction FACET CASES (WHERE name LIKE '%cart%' AS 'cart', WHERE name LIKE '%checkout%' AS 'checkout' WHERE name LIKE '%shipping%' AS 'shipping')`

**FACET CASES (defining brackets)**

`SELECT count(*) from PageView FACET CASES(WHERE backendDuration < 0.5 AS '< 0.5', WHERE backendDuration < 1 as '0.5 - 1', WHERE backendDuration >= 1 as '> 1')`

---
Compare metrics/attributes with multi-function 
---
`SELECT average(backendDuration), average(duration) FROM PageView 
WHERE appName = 'Frontend' TIMESERIES 1 minute`

`SELECT average(duration) AS 'page load', average(pageRenderingDuration) AS 'page render', average(backendDuration) AS 'web app + network' FROM PageView WHERE appName = 'Frontend'`

---
Compare data sets with multi-query / multi-account
---

**Account: Demo Prod**

`SELECT average(duration) AS 'Frontend' FROM Transaction WHERE appName = 'Frontend’ TIMESERIES`

**Account: Other**

`SELECT average(duration) as 'xxxxx' FROM Transaction WHERE appName ='xxxxxxx' TIMESERIES`

---
Funnel
---
`SELECT funnel(session, WHERE pageUrl = 'https://frontend.demogorgon-prod.com/' AS 'Homepage', WHERE pageUrl LIKE '%/product/%' AS 'View product', WHERE pageUrl LIKE '%/cart' AS 'Cart', WHERE pageUrl LIKE '%/cart/checkout' AS 'Checkout') FROM PageView WHERE appName = 'Frontend' SINCE 1 day ago`

---
Histogram
---
`SELECT histogram(duration, 10, 20) FROM PageView SINCE 1 day ago`

---
Heatmap
---
`SELECT histogram(duration, 10, 20) from PageView FACET pageUrl SINCE 1 day ago`

---
Customize widgets
---
`SELECT average(duration) FROM Transaction
WHERE appName = 'Frontend' AND name LIKE '%browse%' SINCE 1 week ago`

---
