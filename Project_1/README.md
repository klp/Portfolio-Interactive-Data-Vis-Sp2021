## Exploration of health data from a mobile app

### Purpose

This project will visualize health data logged from the users of a mobile app called [One Drop](https://onedrop.today/). Users of the visualizations should be able to explore the data in order to reveal patterns in logging behaviors, and provide several portraits of the population of app users. The visualization should be able to provide tools for navigating several categorical variables including logging types, mobile OS, passive vs. active data collection, data source (CGM, meter, data provider integration), diagnosis type, etc.

### Audience(s)

Though the initial audience will include my classmates in our interactive data visualization course, I intend on sharing this exploratory project with a small group of stakeholders for the company I work for. Those stakeholders will be the SVP of data science, the creative director, and the director of analytics. If we use this data for the narrative project, a larger audience within the company will be selected, with the potential of making these data visualizations available to all One Drop employees on our internal blog, and even the public. The designers expect some familiarity with chronic condition management for diabetes, hypertension and prediabetes, though some context may need to be provided in class, and for the general public.

### Source data

The health logging data is currently stored in a couple PostgreSQL database tables. Data is then replicated to a data warehouse to enable analytics/scientific investigation without touching the transactional data or interfere with database performance.


Data will be provided as either 

1. An csv export from our data warehouse, with data cleaned up, wrangled, and transformed with [dbt](https://www.getdbt.com/)
1. A JSON document provided in response to an API request from which the webpage will be able to fetch data, using secrets via [Vault](https://www.vaultproject.io/) for credentialing

### Pre-implementation analysis

Some exploratory statistical analysis will likely be performed before visualization implementation. Knowing the general shape of our data will inform which visualization techniques will be revelatory.

### Mitigating HIPPA concerns

Although explicit approval has been granted by legal, policy and security departments of Informed Data Systems Inc. (my employer), a brief proposal addressing how Private Health Informing (PHI) will be observed will be drafted, reviewed and approved in the last week March 2021. In providing the analysis and visualization of this data, we will satisfy [the HIPPA safe harbor method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#safeharborguidance).

### Security concerns

Discussions are underway as to how best to obfuscate personal identifying fields in the data. Deidentifying strategies may include preprocessing the source data before analysis, or even fetching data from an API in a secure way, which is in keeping with current architectural design. 

### Initial sketches

![different_healthlogging_types](https://user-images.githubusercontent.com/603858/112036050-93ca9280-8b16-11eb-80fe-34aed636f29e.png)

![bloodGlucoseTimeInRange](https://user-images.githubusercontent.com/603858/112036060-962cec80-8b16-11eb-800e-6ead7aa26a58.png)

