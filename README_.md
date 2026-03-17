Business Context

SollmaFin is an international mobile app for online trading of financial assets. Users can invest money in stocks, currencies, cryptocurrencies, exchange-traded funds (ETFs), and other assets. The app's target audience is beginner investors. Access to financial markets is available via smartphone or through the web version.
The app is focused on the Latin American market, with an emphasis on four countries: Mexico, Brazil, Colombia, and Argentina — where interest in fintech and investments is growing rapidly, and the economies are very diverse.

How the App Works
The user downloads the app, registers, goes through a brief onboarding process, and lands on the main page — their personal account.
After this, the user is prompted to fund their brokerage account. Funding a brokerage account is referred to as making a deposit (not to be confused with a bank deposit). The first funding of the brokerage account is the first deposit, the second funding is the second deposit, and so on.
A user can purchase assets with varying degrees of risk:
Low-risk,
Medium-risk,
High-risk.
New user inflow is stable — about 700 installations per day. However, the team noticed that after registration and the first deposit, many users do not purchase assets, and those who have already purchased do not make repeat deposits. Key product metrics are not growing.
A hypothesis emerged regarding users' insufficient financial literacy: they do not understand how to work with assets of different risk levels. Clients buy high-risk assets and lose money, which reduces engagement.
The product team decided to update the user onboarding process and add detailed information about the differences between financial assets and their associated risks. However, there was concern that in-depth onboarding might scare clients away from making deposits and from riskier investments.
To investigate, the team decided to run an A/B experiment.

A/B Experiment
New users who registered in the app from June 2 to June 15, 2025, participated in the experiment.
Users were randomly divided into two equal groups:
The Control Group went through the standard onboarding without mandatory education.
The Test Group went through the updated onboarding with detailed information about assets and their associated risks.

After the split, user activity was analyzed for one week.
The goal of the experiment was to assess how the updated onboarding affects user behavior and their subsequent investment activity.

When implementing the new feature, the product team proposed the following hypotheses:
Growth Hypothesis: Educational onboarding helps users better understand investment principles, so they will be more likely to open a second deposit.
Risk Hypothesis: Information about potential losses and high risks might deter some beginners, especially the most cautious ones, which could reduce conversion to the first deposit.
Additional Hypothesis: After the new onboarding, users who choose high-risk assets will be more likely than before to return and open a second deposit. With the old onboarding, users often purchased high-risk assets without understanding the consequences. This led to losses and churn after the first deposit.

To see the full picture, tracking only conversion metrics is insufficient. The team selected the following set of metrics for the experiment:
Key Metric: Average total deposits per user (including those who installed the app or opened the web version).
Guardrail Metric: Conversion from registration to first deposit.
Secondary Metric 1: Conversion from first deposit to second deposit.
Secondary Metric 2: Average total deposits per user who opened at least one deposit.

It was expected that the key and guardrail metrics would not decline, while the secondary metrics would show significant growth.

Tasks

To conduct a complete analysis of the A/B experiment results. But first, required to dive into the product and study the historical data.

Analysis of Historical Data
To understand why the new feature was developed, is necessary to study the historical data:
Behavior of new users, including acquisition dynamics, segmentation, and key stages of the action funnel.
Metrics related to making deposits, including average deposit amounts.

Analysis of A/B Test Data
Studying the experiment results will consist of two stages:
Comparing user behavior in the control and test groups, assessing the statistical significance of changes.
Investigating the impact of the new onboarding on paying users' behavior. In this investigation, you will use bootstrap and focus on the lower and upper percentiles of the deposit distribution.
Target is to understand how the updated onboarding affected key business metrics, identify growth points, and formulate recommendations for improving user experience and monetization.

Data Description
Two datasets:
The dataset /datasets/pa_sollmafin_hist.csv contains historical data on key actions of new users acquired between April 1 and June 1, 2025, inclusive. The dataset includes user actions up to the moment of making a second deposit.
The dataset /datasets/pa_sollmafin_abt.csv contains A/B experiment data — all actions of new users who registered from June 2 to June 15, 2025, inclusive. The data was collected to test the hypothesis about the impact of the new onboarding on user behavior and activity. Users are already assigned to A/B experiment groups.

Common Fields in Datasets:
user_id — unique user identifier;
country_code — user's country code in ISO format (e.g., BR — Brazil, MX — Mexico, AR — Argentina, CO — Colombia);
platform — device the user interacts with the product on: mobile or web;
first_ts — timestamp of the user's first appearance in the system;
first_dt — date of the user's first appearance (without time);
event_ts — timestamp of the event;
event_name — name of the event;
amount — deposit amount;
asset — type of asset purchased;
risk_level — risk level of the asset: low (low risk), medium (medium risk), high (high risk).
The dataset /datasets/pa_sollmafin_abt.csv contains two additional fields:
ab_test — name of the A/B experiment;
group — user's A/B experiment group.
