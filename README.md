# TELECOMMUNICATION-SUBSCRIBER-CHURN-ANALYSIS


# TABLE OF CONTENTS
- [BACKGROUND](background)
- [DATA STRUCTURE](data-structure)
- [EXECUTIVE SUMMARY](executive-summary)
- [INSIGHTS DEEP DIVE](insights-deep-dive)
- [RECOMMENDATIONS](recommendations)
- [ASSUMPTIONS AND CAVEATS](assumptions-and-caveats)


## BACKGOUND

FiberTel is a fictitious internet service provider (ISP) and a major provider of Fiber-to-the-Home (FTTH) premium broadband in Africa and Europe. We deliver excellent fiber internet services across homes and offices with a triple-play service comprising broadband, voice, and video. Our cutting-edge technology can guarantee low latency and optimal speed.

As pacesetters, FiberTel has consistently deployed high-end, ultramodern technology to serve the rapidly emerging digital environment of netizens. With current expansions to key economies like Germany, France, and Spain in Europe, we aim to serve our ever-growing network of homes and businesses.

Over the past 7 years, we have focused on nurturing the relationship we have with our subscribers. We are constantly discovering innovative and affordable ways to create more value and meet the needs of our subscribers.

Our team of experts at FiberTel is well equipped to deliver a quality fiber-optic broadband experience. We are poised and structured to deliver a quality, fiber-optic broadband experience at a low cost to your home or office through our unique products: fiber-to-the-home (FTTH) and fiber-to-the-office (FTTO).

This report analyzes customer attrition trends across FiberTel’s newly expanded European markets—Germany, Spain, and France—over a 10-tenure period. It identifies key factors driving subscriber churn, highlights high-risk demographic segments, and presents data-informed strategies to improve retention and reduce churn across these regions.



### Insights and recommendations are provided on the following key areas:

1.	**Subscriber churn analysis:** An analysis of churn in relation to age, gender, salary category, and country to identify high-risk segments
   
2.	**Customer segmentation and demographics:** By segmenting customers based on age and gender and exploring how these factors intersect with salary categories and churn outcomes.

3.	**Geographic & Tenure Trends:** An examination of country-level demographics and tenure history to uncover regional patterns in churn and customer lifespan.


Source data from kaggle database used for analysis can be accessed [HERE](https://www.kaggle.com/datasets/synful/churn-data/data)

The python changelog script used in inspecting and cleaning the data and preparing it for analysis can be found [HERE](https://github.com/paschaldubem/TELECOMMUNICATION-SUBSCRIBER-CHURN-ANALYSIS/blob/main/Customer_churn.ipynb)

Targeted python code base regarding various business questions can be found [HERE](https://github.com/paschaldubem/TELECOMMUNICATION-SUBSCRIBER-CHURN-ANALYSIS/blob/main/Customer_churn.ipynb)

An Interactive Looker Studio dashboard used to report and explore key factors contributing to churn can be found [HERE](https://lookerstudio.google.com/s/r_MA3UJ2fug)



## DATA STRUCUTRE 

The FiberTel database, as seen in the image below, consists of one table containing 10,000 unique subscriber records across 15 columns. A description of each column is as follows:

![CUSTOMER CHURN EXCEL SHEET ](https://github.com/user-attachments/assets/c6d3d7b5-71b5-4a57-a8fd-37b8927b54ea)

- **CUSTOMERID:** Unique identifier assigned to each subscriber. 
- **SURNAME:** Last name of the subscriber (used for recordkeeping, not analysis).
- **CREDIT SCORE:**  A numerical indicator of the subscriber’s creditworthiness based on their financial history.
- **GEOGRAPHY:** Country of residence where the subscriber accesses our services (e.g., Germany, France, Spain).
- **GENDER:** Biological sex of the subscriber (Male or Female)
- **AGE:** Subscriber’s age in years
- **TENURE:** Duration of the subscriber’s relationship with FiberTel, measured in months.
- **BALANCE:** Total lifetime spend by the subscriber on FiberTel services.
- **NUMBER OF PRODUCTS:** Number of distinct services the subscriber is enrolled in.
- **HAS CREDIT CARD:** Indicates whether the subscriber has a credit card on file (Yes/No)
- **IS ACTIVE MEMBER:** Reflects whether the subscriber is currently active based on engagement behavior.
- **EXITED:** Churn status—denotes if the subscriber has churned (1) or is retained (0).
- **AGE GROUP:** Categorical age bracket assigned to the subscriber.
- **SALARY CATEGORY:** Categorical salary bracket indicating the subscriber’s income level.


## EXECUTIVE SUMMARY 

### Overview of findings

**FiberTel’s overall churn rate stands at 20.4%**, more than double the FTTH industry average of approximately 9%. Analysis indicates that the primary contributors to this elevated churn are **middle-aged, high-income female subscribers in Germany**. This group is likely more susceptible to switching providers due to their **greater purchasing power and the absence of proper telecom infrastructure to offer quality service and tailored, age-specific plans within our current offerings**. To mitigate this trend, targeted retention strategies should be developed to address the needs and expectations of this segment. Additional high-risk subscriber groups are identified and discussed in detail in the following section.

Below is a churn overview page from one of the Looker Studio dashboards; more examples are included throughout this report. The dashboard can be previewed [HERE](https://lookerstudio.google.com/s/r_MA3UJ2fug)

![customer churn dashboard ](https://github.com/user-attachments/assets/9ec8756d-5ff3-461b-819b-09f02f9cb32e)


## INSIGHTS DEEP DIVE 

### SUBSCRIBER CHURN ANALYSIS
   
- **The churn rate of 20.4% indicates that 1 in 5 customers discontinued service over the past 10 tenure periods**—more than double the FTTH industry average. This elevated attrition is likely driven by strong competition and superior service coverage offered by alternative providers in the region.

- Despite representing a smaller share of the customer base **(45% vs. 55% male), female customers exhibited a higher churn rate at 25% (1,139)**, compared to **17% (898) for male customers**. Notably, 83% of male subscribers were retained, suggesting a gender-based retention disparity. These findings underscore the need for more targeted retention strategies focused on female subscribers.

![CHURN BY GENDER BREAKDOWN](https://github.com/user-attachments/assets/b86d1f40-0093-4150-8510-9ab9f12f3528)

- Churned customers were, on average, **8 years older than those retained (approx. 45 vs. 37 years)**, suggesting that older subscribers are more prone to churn—potentially due to evolving service expectations or unmet needs.

To deepen the analysis, the customer base was segmented into three key age categories:
-    Young Adults (18–35)
-    Middle-Aged (36–60)
-    Seniors (61+)

**The middle-aged segment forms the largest share of our customer base at 53.8%**, indicating strong product-market fit with this group. However, this segment also **recorded the highest churn rate at 29% (1578)**, nearly three times that of **young adults (8%, 347)**, and slightly higher than **seniors (25%, 115)**. This may reflect higher service expectations among working-age adults, making them more likely to churn if performance does not meet their standards.

While seniors churn at a lower rate than middle-aged adults, their churn level remains relatively high. This may be attributed to a lower likelihood of returning to incumbent providers once they switch, possibly due to reduced service familiarity or comfort with change.

Conversely, **young adults demonstrated the highest loyalty, with 92% (3806) retained**, making them a high-potential segment for long-term engagement and growth through focused marketing and retention efforts

![CHURN BY AGE CATEGORY](https://github.com/user-attachments/assets/5be40f7f-fb16-41a1-9e77-627d8cd68161)

- **Germany exhibits the highest churn rate at 32%, with 814 customers exiting**, significantly outpacing **France (16%, 810) and Spain (17%, 413)**. Although France accounts for 50% of the total customer base, and Germany and Spain each represent approximately 25%, the churn volumes in Germany and France are nearly identical in absolute terms.

However, when normalized against customer base size, Germany’s churn rate is disproportionately high, highlighting a critical retention issue in this market. This suggests that churn in Germany is not merely a function of volume but of deeper market-specific challenges requiring targeted investigation and intervention.

![CHURN BY COUNTRY](https://github.com/user-attachments/assets/88196fa0-09de-4b85-a174-366f59e21674)

-  **Customer acquisition surged at the start of our campaign, followed by a relatively stable churn trend across the 10-tenure period**. Churn peaked during the first tenure (232), likely due to non-conversion of trial users who opted out after the 1-month free trial.

Another notable spike occurred in the **ninth tenure (213)**, coinciding with increased market competition from mobile broadband providers. This trend continued into the tenth tenure, contributing to a sustained decline in subscriber retention during the campaign’s later stages.

![TENURE CHURN TRENDS ](https://github.com/user-attachments/assets/686968eb-ed60-4d70-a819-ca3f582c83e9)

- Subscribers were segmented into three salary brackets
  
a.	Low Salary: $11.58–$66,671.88

b.	Medium Salary: $66,671.88–$133,332.18

c.	High Salary: $133,332.18–$199,992.48

**High-salary earners exhibited the highest churn rate at 21% (701 customers) and the lowest retention (79%)**. This trend suggests that these customers, likely residing in urban areas with abundant service options, are less price-sensitive and more influenced by competing offers—particularly from quadruple-play and mobile broadband providers.

Conversely, medium- and low-salary earners showed higher retention levels (≈80%), indicating greater price-value satisfaction and alignment with our current service offerings.

![CHURN BY SALARY CATEGORY](https://github.com/user-attachments/assets/42b22257-7c26-404c-9c91-302834866617)


### CUSTOMER SEGMENTATION AND DEMOGRAPHICS
   
- **Our subscriber base is predominantly male (55%), with male customers outnumbering females across all age segments**—including young adults, middle-aged, and seniors. The middle-aged male population (2,885) is notably larger than the female equivalent (2,498).
  
- **The 36–60 age bracket (middle-aged) represents the majority of our customer base**, accounting for 53% of total subscribers. Young adults (18–35) and seniors (60+) make up 41.5% and 4.7%, respectively.

- **Subscribers with credit scores below 650 demonstrated a slightly higher propensity to churn**, indicating a potential link between financial risk profile and loyalty.
  
- **Men outnumber women across all salary brackets, averaging over 1,800 male customers per bracket compared to 1,500 women**. However, when analyzed proportionally:
  
a.	34% of female customers fall into the medium salary category, compared to 33% of males.

b.	Males lead in the low-income category, with 34% of their population falling below the medium salary threshold.

- **Our middle-aged customers also make higher salaries, outpacing the younger and senior age groups by population in this category**, i.e., in the high salary category, middle-aged (1768) to young adults (1391). This suggests greater affluence among the core demographic, potentially influencing churn patterns and service expectations.


![customer churn dashboard 4](https://github.com/user-attachments/assets/bc93f809-27a7-41bb-a2ac-0c63592a77b6)

   
### GEOGRAPHIC & TENURE TRENDS: 
   
- **French customers demonstrate stronger long-term engagement, maintaining a consistent subscriber count between 500 and 600 over the 10-month period**. In contrast, Germany and Spain each averaged 200–300 customers, suggesting higher retention and brand affinity in France compared to the other regions.
  
- **France is our largest customer base, with an even gender split (50.4% male, 49.7% female)**, reinforcing its status as our core market. Notably, a larger share of female customers reside in Germany (26%) compared to males (24%)—a country already identified as having the highest churn rate.
  
- **Middle-aged customers (36–60) form the dominant segment across all three countries, with Germany having the highest proportion (57%)**. Meanwhile, France hosts the youngest customer base, with 43% aged 18–35, reaffirming the strategic importance of middle-aged customers to overall performance.
  
- **Across the 10-tenure period, female subscriber counts remained consistently lower than male counts at each time point**. This persistent gap highlights an opportunity to improve gender balance in subscriber acquisition and retention.

![customer churn dashboard 3](https://github.com/user-attachments/assets/e47dab7d-8706-46bb-be5c-cedc5991bc6d)


## RECOMMENDATIONS 

Based on the key insights from this analysis, the following strategic recommendations are proposed for the marketing and engineering teams.

- To reduce churn in Germany and boost retention instead, **we need to build out our current telecoms infrastructure in Germany or engage in collaborative agreements to share FTTH networks, fostering wholesale business models, and introduce exclusive perks, loyalty programs, and promotional bundles to incentivize long-term customer retention**. As the FTTH coverage in Germany is at 40%, with 60% of the country still underserved and growing take-up rates, this represents a massive market opportunity for us operators for competitive positioning.
  
- High-income customers churn at a disproportionately higher rate (21%), driven by increased competition and lower price sensitivity. **We need to offer premium bundle offers and value-added services such as VOIP (Voice Over IP) and smart home solutions and apply targeted marketing campaigns with priority customer service**, which would make us attractive to customers over mobile broadband networks or other fixed broadband operators offering quadruple play tariffs.
  
- Middle-aged women represent a key at-risk demographic, and if we want to retain them, **we need to focus on targeted, age-appropriate, personalized incentives for women in that age bracket**.

- With a strong 92% retention rate, young adults are our most loyal segment, which is great and can be maintained and improved upon by **investing in digital marketing, social media influencer partnerships, and launching youth-focused loyalty programs to deepen brand engagement and attract new users in this segment**.



## ASSUMPTIONS AND CAVEATS 

To manage data limitations and ensure analytical clarity, the following assumptions were made during the course of this analysis:

- The unit of measurement for customer tenure was not explicitly defined. For the purpose of this analysis, tenure was assumed to be measured in months.
  
- The churn status variable was originally encoded in binary format (1 = churned, 0 = retained). These values were recoded as 'Churned' and 'Retained,' respectively, to enhance interpretability in visualizations and reporting.






