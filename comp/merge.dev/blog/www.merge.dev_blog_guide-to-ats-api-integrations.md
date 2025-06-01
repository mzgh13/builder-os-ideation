---
url: "https://www.merge.dev/blog/guide-to-ats-api-integrations"
title: "ATS integration: definition, examples, and tools"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-ats-api-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-ats-api-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-ats-api-integrations#)

Table of contents

[What are ATS integrations?](https://www.merge.dev/blog/guide-to-ats-api-integrations#what-are-ats-integrations)

[What are the top ATS APIs?](https://www.merge.dev/blog/guide-to-ats-api-integrations#what-are-the-top-ats-apis)

[Key applicant tracking concepts](https://www.merge.dev/blog/guide-to-ats-api-integrations#key-applicant-tracking-concepts)

[ATS API data schemas](https://www.merge.dev/blog/guide-to-ats-api-integrations#ats-api-data-schemas)

[Top ATS API use cases](https://www.merge.dev/blog/guide-to-ats-api-integrations#top-ats-api-use-cases)

[Approaches for implementing customer-facing ATS integrations](https://www.merge.dev/blog/guide-to-ats-api-integrations#approaches-for-implementing-customer-facing-ats-integrations)

[Getting started with ATS APIs](https://www.merge.dev/blog/guide-to-ats-api-integrations#getting-started-with-ats-apis)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-ats-api-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7438e1085d0d6f5a4b_13.webp)**5 recruiting integrations that can boost the candidate experience**](https://www.merge.dev/blog/recruiting-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**How to read API documentation**](https://www.merge.dev/blog/how-to-read-api-documentation)

# ATS integration: definition, examples, and tools

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cede4e321d978c2aa62_Lead_API.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53831f80f118f3af61fa_62eff2893d1cea398f23f57b_Shensi.webp)

Shensi Ding

CEO and co-founder

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 40+ recruiting integrations with one_ [_ATS API_](https://merge.dev/categories/ats-recruiting-api).

The recruiting market has changed a lot over the past few years. The recruiting space has had [significant innovation](https://future.com/deep-job-platforms/) and new companies continue to enter the recruiting tech market, from AI-based candidate sourcing to job placement solutions for market verticals. In just the past few years, Gem, SmartRecruiters, Jobandtalent, Workrise, SeekOut, and Handshake have [all raised more than $100M](https://pitchbook.com/news/articles/human-resources-hr-venture-capital-diversity-remote-work).

The demand for new recruiting solutions makes integrations with existing applicant tracking systems (ATS), designed to follow candidate progress through the recruiting process, ever more important. Integrating with ATS systems and powering the boom in recruiting tech software are ATS APIs.

Read on for a guide on everything you need to know about ATS APIs:

- **Top ATS APIs** \- Which ATS’s matter most
- **Key concepts** \- How an ATS works
- **Data schemas** \- How various providers organize candidate and job data
- **Use cases** \- Common ways in which ATS data is used in product integrations
- **Getting started** \- Approaching ATS integrations to your product

## What are ATS integrations?

An [API integration](https://www.merge.dev/blog/api-integration) is the process of connecting two or more applications using an API and letting them share data and functionality with each other. [ATS integrations are oftentimes required for recruiting products](https://www.merge.dev/blog/api-integration-benefits), because there is so much data that is continuously being updated in various systems and the use case of recruiting requires continuously updated and synced data. Especially because the number of candidates that need to be synced for even a small company could be in the thousands, many products are deemed unusable without long-term integrations.

For example, if there was a sourcing product that didn't integrate with an ATS, after a candidate is sourced, the recruiter would have to manually enter the candidate's name, role, LinkedIn, and other details into the ATS. This would be a huge pain for the recruiter, and be an absolute blocker for adoption.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4133e8008fe7cf11b35_65486df406d09ec51af1edce_Screenshot%25202023-09-14%2520at%25209.21%25201.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4133e8008fe7cf11b35_65486df406d09ec51af1edce_Screenshot%25202023-09-14%2520at%25209.21%25201.webp)

#### Integrate with every ATS through Merge

Learn how Merge's Unified API lets you integrate your product with dozens of ATS solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-ats-api-integrations)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## What are the top ATS APIs?

The applicant tracking system (ATS) landscape is broad, with nearly 10 different ATS’s representing 80% of the market share for mid-market and enterprise recruiting. ATS systems focused on SMBs make up an even larger, more fragmented market. Longstanding ATS systems - IBM, **UKG** (Ultimate), and **Ceridian** \- have been joined in the 2000s by SaaS-first products such as **Taleo**, **SuccessFactors**, **Workday**, **Jobvite**, and **Cornerstone**. The latest crop of ATS systems from the 2010s include **Greenhouse**, **Lever**, and **SmartRecruiters**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4133e8008fe7cf11b2b_6334ad714b82a8dcccabb8d0_ATS%2520Systems%2520by%2520Market%2520Share.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4133e8008fe7cf11b2b_6334ad714b82a8dcccabb8d0_ATS%2520Systems%2520by%2520Market%2520Share.webp)

Source: [Ongig](https://blog.ongig.com/applicant-tracking-system/top-applicant-tracking-systems-ats-software-2020/)

‍

## Key applicant tracking concepts

While most ATS concepts are relatively straightforward, there are a few key dimensions along which ATS APIs vary. You’ll want to keep these in mind as you access ATS APIs across the various vendors.

### **Requisitions, jobs, and postings**

Most ATS’s have multiple concepts related to what we think of an ‘open position’.

Typically a requisition is a job template, containing information about the job requirements and hiring process (scorecards, interviews, etc.).

Each requisition may have multiple jobs concurrently or over time, typically one for each person to be hired. In some ATS’s like Lever, a job can be assigned to multiple requisitions when unique requisition IDs are required. Other ATS’s like Greenhouse accomplish this with a single requisition but multiple ‘opening IDs’. Greenhouse calls a requisition a ‘job’ and each opening a ‘job opening’.

For each job, there may be none, one, or multiple job postings that we’d typically expect to see listed on a company’s careers page.

### **Sourcing leads and prospects**

Some ATS systems include sourcing capabilities, where a recruiter will reach out to prospective candidates to inform them of the job opening and encourage them to apply. These prospects are often treated separately in the API. For example, in Greenhouse ‘prospects’ are accessed using the same GET endpoint as ‘candidates’, where they aren’t associated with an application (unlike ‘candidates’). However, ‘prospects’ are created using a distinct POST endpoint from ‘candidates’. Some platforms such as Lever refer to prospects as ‘leads’.

### **Mapping candidates to their applications**

Candidates form the primary data object in an ATS (they are applicants being tracked). Many APIs have distinct concepts for the candidate (demographic info, contact info) and the instance of a candidate applying for a specific job. In the case of Greenhouse these concepts are called ‘candidates’ and ‘applications’, respectively. L

ever approaches it differently; it has a ‘contact’ that is associated with multiple ‘opportunities’ (instances of the contact applying).

One further difference, when an ATS is part of a broader HRIS package, is how they treat the workflow from candidate to employee. Workday and SAP, for example, can associate a job requisition (and hence a candidate) with an employee that was hired.

### **Active and archived candidates**

Over time an ATS has a lot, in some cases millions, of applicants that have applied to jobs over time. Which candidates are active, typically the ones you’re interested in, is an important dimension to understand for each API.

## ATS API data schemas

[**Candidates**](https://merge.dev/docs/ats/candidates) represent individuals who apply or are referred for jobs (or in some cases may be recruiting prospects). This object includes contact information: location, phone numbers, emails, and social profile URLs.

Sensitive demographic information for each candidate is typically stored in an [**EEOC**](https://merge.dev/docs/ats/eeocs) (named after types of discrimination prohibited by the US Equal Employment Opportunity Commission) object or field, with data about race, gender, veteran status, and disability status. Each candidate may also have a set of [**Attachments**](https://merge.dev/docs/ats/attachments) such as resumes, cover letters, or portfolios.

Each candidate is typically associated with one or several [**Applications**](https://merge.dev/docs/ats/applications) for jobs they have applied to. The application object includes the application date/time, rejection date/time and reason, source, and the current stage.

Each application is associated with a [**Job**](https://merge.dev/docs/ats/jobs) (aka requisition) that represents an open position a company is looking to fill. The job will typically include the departments it is part of, the [**Offices**](https://merge.dev/docs/ats/offices) where the job will be performed, the hiring manager, recruiters, job description, job code, and the status of the job (open, closed, filled).

Each application also has a set of [**Interviews**](https://merge.dev/docs/ats/interviews) that correspond to [**Job Interview Stages**](https://merge.dev/docs/ats/job-interview-stages). The Interviews object commonly contains information about interviewers, location of the interview, start and end time, and the status of the interview. Each interview typically contains [**Scorecards**](https://merge.dev/docs/ats/scorecards) per interviewer with timestamps and the interviewer's recommendation.

Each ATS also keeps track of communication with a candidate. [**Activities**](https://merge.dev/docs/ats/activities) such as notes, emails, and comments can be associated with a variety of ATS objects: candidates, applications, and interviews. Each Activity contains data about the activity type, subject, and body.

Finally, when a candidate’s Application makes it all the way through a successful interview process they receive [**Offers**](https://merge.dev/docs/ats/offers). The Offers object contains information about when the offer was sent, when the offer closed, the start date, and the offer status.

‍

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4133e8008fe7cf11b3a_6334adea317c0b54a295ef3e_Object%2520Table.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4133e8008fe7cf11b3a_6334adea317c0b54a295ef3e_Object%2520Table.webp)

‍

## Top ATS API use cases

### **Job boards and company directories**

Attracting candidates starts with having job listings and company profiles easily accessible. ATS products integrate with job ad platforms, job boards, and company profile sites to sync current job openings.

Examples: Indeed, Talent.com, The Org, ZipRecruiter, Comparably, The Muse, AngelList

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a8481b602592e59e1965_kgV4-ZgSEHyTt4_6LLz_-2S9BGLDzO7LAijhGxQVhiRneSb88vLYnFLScJCbNrkaYoy_mDVgJokKnNAuhiYe3Mzx_Bw-g8s3jpW3MWDBR9TLO9Ka81tBLh6Z7H02ZSLIduNFj7ULwzSIgIB5nCymXBl4uqHKLiE6BxZuNhdzX3FA39Hb_P9ACnhQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a8481b602592e59e1965_kgV4-ZgSEHyTt4_6LLz_-2S9BGLDzO7LAijhGxQVhiRneSb88vLYnFLScJCbNrkaYoy_mDVgJokKnNAuhiYe3Mzx_Bw-g8s3jpW3MWDBR9TLO9Ka81tBLh6Z7H02ZSLIduNFj7ULwzSIgIB5nCymXBl4uqHKLiE6BxZuNhdzX3FA39Hb_P9ACnhQ.webp)

Lever exports open jobs to AngelList and then imports the candidate’s details if they’re interested.

### **Candidate sourcing**

Building a candidate pipeline is a critical part of recruiting. Sourcing apps integrate with ATS tools to add candidate data for outreach, recommend candidate matches, coordinate employee referrals, and kick off initial recruiting screens.

Examples: Gem, Teamable, Circular, Dover, Fetcher, Handshake, LinkedIn, Ripplematch

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84848749308dbfa94c6_jvlOWN2v4fo8H_543-YImjXyiQtNXxILwRjRIhbaivKqy9t8puRe3M0WWROThqiqU6fxzAjcYLOxN2fS4J59_kt-r776VEWlKMndiCFyIBfIh_J8jc0rvzbRwIefQfUxuu57dVQ_SLIREm0-78IkTdwhzhef7lPDDPk-CLmAWY1NtLzS98v73ElN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84848749308dbfa94c6_jvlOWN2v4fo8H_543-YImjXyiQtNXxILwRjRIhbaivKqy9t8puRe3M0WWROThqiqU6fxzAjcYLOxN2fS4J59_kt-r776VEWlKMndiCFyIBfIh_J8jc0rvzbRwIefQfUxuu57dVQ_SLIREm0-78IkTdwhzhef7lPDDPk-CLmAWY1NtLzS98v73ElN.webp)

Gem integrates with SmartRecruiters to access existing candidate data and to add new candidates to the ATS.

### **Interview assessments, scheduling, and expenses**

Coordinating interviews is complex and, unsurprisingly, many products help make the interview process more efficient. Video interviewing, virtual skills assessments, scheduling apps, travel and expense management, and surveying tools integrate with ATS products to streamline interviewing.

Examples: Bryq, Codility, HackerRank, TestGorilla, Brighthire, Expensify, Calendly

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a848b9252db56ce14719_eJFpkRyWW4kJ1i3Lt6GNiiOwMzRL8aDfMcEx2E86Y1eoCo2aFANwarBVDOp8xqWyos-xoke7IippwHKj08KOzRHTESq8-g6l-muCaUbFvIz7bL81tk_1Gvlv2Jo1CpB8lWwDuNS5QpPGkCZr-Iq7_lQAA1PESfHc3xifjmkQDXFsXmuWZwZP8OF-.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a848b9252db56ce14719_eJFpkRyWW4kJ1i3Lt6GNiiOwMzRL8aDfMcEx2E86Y1eoCo2aFANwarBVDOp8xqWyos-xoke7IippwHKj08KOzRHTESq8-g6l-muCaUbFvIz7bL81tk_1Gvlv2Jo1CpB8lWwDuNS5QpPGkCZr-Iq7_lQAA1PESfHc3xifjmkQDXFsXmuWZwZP8OF-.webp)

BreezyHR integrates with HackerRank to perform coding assessments and advance applicants through the hiring process.

### **Candidate communication**

Communicating effectively with candidates is key to move applicants through the hiring process. ATS’s integrate with communication apps to streamline email and text messaging and perform analytics on the candidates’ interactions.

Examples: Grayscale, Mixmax

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84982c5906352f75b75_CBdR6ehs9_w7KF70TrFx7DBlZs0nDJqUzCEmwNzwFeQnkUW8IuTxi2B_w39Zvu3XIwwFbt1-IEaHExqQzlie9zmDZA8JtIUu2iYmmIIg-jj_Dhgy52C4exbrg3PUMGF2kU-kpwfbpr1hdC0hK6R_glVXoPeeWiKWGnDd1g3M8bhv_hbrqlsM-VZR.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84982c5906352f75b75_CBdR6ehs9_w7KF70TrFx7DBlZs0nDJqUzCEmwNzwFeQnkUW8IuTxi2B_w39Zvu3XIwwFbt1-IEaHExqQzlie9zmDZA8JtIUu2iYmmIIg-jj_Dhgy52C4exbrg3PUMGF2kU-kpwfbpr1hdC0hK6R_glVXoPeeWiKWGnDd1g3M8bhv_hbrqlsM-VZR.webp)

Grayscale integrates with Greenhouse to communicate with candidates via text messages.

### **Offer screening and signing**

During the offer process multiple steps are typically required, including background checks, employment checks, authorization of work (I-9, e-verify), reference checks, and electronic signatures. Syncing offer-stage candidates from an ATS system, and then updating the offer status once the check is complete, automates the hiring workflow.

Examples: Checkr, Equifax, HiPeople, Docusign, AdobeSign

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84803c77c2c29db1731_RJyQN8HH3KCLLnYGxrVdwPw2orOKzcsGZkpWIOYIn6gJ28eOFKnxMrNO7rboMk3tvOWEWRiNFFGRrVRH38jw5kfIeBEyuDUjf4jkZjnE_Wfrcws2Mvz-iCsPoQyiyXw9zJkPL__2UfkJofDS_mnokCPpv_cJWYSiqNhq4ebdvzvHHGtcOskQgtsD.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84803c77c2c29db1731_RJyQN8HH3KCLLnYGxrVdwPw2orOKzcsGZkpWIOYIn6gJ28eOFKnxMrNO7rboMk3tvOWEWRiNFFGRrVRH38jw5kfIeBEyuDUjf4jkZjnE_Wfrcws2Mvz-iCsPoQyiyXw9zJkPL__2UfkJofDS_mnokCPpv_cJWYSiqNhq4ebdvzvHHGtcOskQgtsD.webp)

Workday integration with Docusign to sign offer letters and other onboarding docs.

### **HR and onboarding**

Once an offer is accepted, companies want to have a seamless onboarding process. ATS products sync new hire data to HR and payroll systems to kick off employee onboarding.

Examples: Personio, Wurk, Deel, Remote

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84803c77c0714db175a_JqbQiBRMx162f8MenxYxvn0LAIv3BbFUmYSIiuiju_0ZPuFs9OB94mKS95t_f-_LSns9QKCb3-sAaxLZhe1nnMTN_usncnZLKzNeKgsFST5hkp3IFjPska35TEE7PjxWDHNzEwqu_J_AAF7bv4SJaikFBJgucb9Mhc94mRLpnW2EhOl6zvMcc1e-.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84803c77c0714db175a_JqbQiBRMx162f8MenxYxvn0LAIv3BbFUmYSIiuiju_0ZPuFs9OB94mKS95t_f-_LSns9QKCb3-sAaxLZhe1nnMTN_usncnZLKzNeKgsFST5hkp3IFjPska35TEE7PjxWDHNzEwqu_J_AAF7bv4SJaikFBJgucb9Mhc94mRLpnW2EhOl6zvMcc1e-.webp)

Teamtailor ATS integration that sends new hires to Personio HR for onboarding.

### **Hiring analytics**

Recruiting analytics are a powerful way to optimize the hiring process. Common ATS integrations sync open roles, hired roles, and interview metrics to track headcount planning, DEI initiatives, and employee interview training.

Examples: ChartHop

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84819451d574d2320a2_g40PvUvkdL36RWUx1v8sPGX6UNZgNIxIfRFW5lgs-TeHiAVYqptVwzTzRSxvIHdxv065q6E4qQbY98yx9A1Ue_4TNWgeoMXiPBLIOyMPwDjbOOOk-Qwuk0HYC2m3D6YSPB39SPvwboDIBxEZcSR6fn37eQ6XNNVgrv2rHTMYyv9ZsoJ3fCoGnKF8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6334a84819451d574d2320a2_g40PvUvkdL36RWUx1v8sPGX6UNZgNIxIfRFW5lgs-TeHiAVYqptVwzTzRSxvIHdxv065q6E4qQbY98yx9A1Ue_4TNWgeoMXiPBLIOyMPwDjbOOOk-Qwuk0HYC2m3D6YSPB39SPvwboDIBxEZcSR6fn37eQ6XNNVgrv2rHTMYyv9ZsoJ3fCoGnKF8.webp)

ChartHop syncs jobs from Greenhouse to report on headcount and recruiting analytics.

### **ATS integration benefits**

Here are some of the benefits of ATS integrations:

#### **Prevents human errors**

Requiring your recruiters or clients to copy and paste information to and from an ATS manually can introduce a host of costly errors.

This can be provisioning employees with the wrong level of access to an application, which, in turn, allows them to access data and actions in that app that’s not meant for them; it can be marking a candidate as rejected when they're actually still in process, which sends them a rejection email accidentally which creates a poor candidate experience; or it can be putting the wrong name for a candidate, which can lead to confusion—and the list goes on.

Since ATS integration streamlines data entry, your employees or clients don’t have to worry about any of the negative outcomes described above.

#### **Provides a great customer experience**

By allowing clients to automatically sync candidate data with your product, you can sync candidate and application data on time and without any friction; ensure that every application has the correct stage and notes in your product; set off the appropriate workflows for each candidate; reject or move forward candidates in your product based on the corresponding changes in the client’s ATS, etc.

All of this translates to happier clients that are more engaged in your product and are more likely to renew and spend more on you.

#### **Delivers an improved employee experience**

Enabling employees to avoid copying and pasting data between applications not only prevents them from carrying out tedious, mundane work but also lets them focus on tasks they enjoy and are uniquely positioned to tackle. And by letting employees focus on more interesting, strategic work, they can be happier at your organization—making them [more productive](https://www.ox.ac.uk/news/2019-10-24-happy-workers-are-13-more-productive).

#### **Offers scalability**

By using a [unified API](https://www.merge.dev/blog/universal-api), you can simply build to a single API to offer dozens of customer-facing ATS integrations. This limits the time your developers have to spend on building your integrations and it ensures you’re able to offer all the integrations your clients and prospects need.

[![A visual of how universal APIs work](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64ca89b1e6bb722305f6c535_IvIinQ4nKOc_1L7fJBA5ZGmshyjB5ZS-Y7dLfMhI3dSOYGfxXzPa6aKR4PJfnC590aN7vkkv4Tr5h4BZo9OcGrgvd6sHje7phP8sg9hYhEc80RNG-RE7fI3OfVvIuxVjQYNQiPQcgq-JR9v8Zg4WP1ISQQ%3Dnw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64ca89b1e6bb722305f6c535_IvIinQ4nKOc_1L7fJBA5ZGmshyjB5ZS-Y7dLfMhI3dSOYGfxXzPa6aKR4PJfnC590aN7vkkv4Tr5h4BZo9OcGrgvd6sHje7phP8sg9hYhEc80RNG-RE7fI3OfVvIuxVjQYNQiPQcgq-JR9v8Zg4WP1ISQQ%3Dnw.webp)

_Using Merge’s_ [_ATS Unified API_](https://www.merge.dev/categories/ats-recruiting-api) _, you can access 40+ ATS integrations_

In addition, the unified API solution can make the process of managing and performing maintenance on these integrations easy by offering fully-searchable logs and features like automatic issue detection.

[![A screenshot of a bad API key error message from Merge's Dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2959df7dd916026443516_iCmrcQ2I5eRTg_7pjcIZFRyRp7sy1v766qinGPHB-LV0EvqTFLUcX3SomLX_3lOD15csSNxZdtna5hJB8QwYMd9d3qI_bg1HViBmyhBOaSMFu-wMmA40KgKbjlRhvFWYOkoVtcjzBTfgkfcMhKD7UFk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2959df7dd916026443516_iCmrcQ2I5eRTg_7pjcIZFRyRp7sy1v766qinGPHB-LV0EvqTFLUcX3SomLX_3lOD15csSNxZdtna5hJB8QwYMd9d3qI_bg1HViBmyhBOaSMFu-wMmA40KgKbjlRhvFWYOkoVtcjzBTfgkfcMhKD7UFk.webp)

_You can automatically identify specific integration issues and uncover the steps to remediate them in Merge’s Dashboard_

## **Approaches for implementing customer-facing ATS integrations**

Now that you know why ATS integrations and the major players and data scehamas, the next question you’re likely asking is how, exactly, you can go about implementing them.

Here are a few options to help guide your evaluation.

### **In-house development**

In-house development involves assigning your in-house engineering team to build integrations to 3rd-party APIs and [to maintain the integrations in an ongoing basis](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance).

[![A visual representation of native integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c800f7a1ba75ef75afe04f_DH7Wk851OSYwQ-ZWe93ncg7CDUc1n4csBbl9_ZHRYX3z1vFghCBacSdAuzhCdg5bJbl1pdTVPHi6p45qxW9iA4nBeEe_yzRgFbK5y1omh4DCO2eTDK7JBckjbNWm_ynXbgM33bx_-CGXZWn6EQrC7ew.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c800f7a1ba75ef75afe04f_DH7Wk851OSYwQ-ZWe93ncg7CDUc1n4csBbl9_ZHRYX3z1vFghCBacSdAuzhCdg5bJbl1pdTVPHi6p45qxW9iA4nBeEe_yzRgFbK5y1omh4DCO2eTDK7JBckjbNWm_ynXbgM33bx_-CGXZWn6EQrC7ew.webp)

There are certainly some benefits to this approach. For instance, it allows you to avoid working with 3rd-parties. In addition, it can prove manageable if you only need to build one integration or the integrations you need to build are relatively shallow in scope.

However, in reality, you’ll likely need to implement and maintain an ever-growing set of robust integrations. Tasking your developers with this would take up most of (if not all of) their time, forcing them to forgo other critical work, such as addressing product bugs or developing key features for your product. In addition, integrations require a lot more time to maintain than to build initially, so you will likely have to hire a team that will be maintaining these integrations in an ongoing basis.

### **Embedded integration platform as a service (iPaaS)**

Embedded iPaaS is a newer option that started in the mid 2010s when iPaaS providers were asked if their solutions could help with product integrations. An [embedded iPaaS](https://merge.dev/blog/embedded-ipaas) is a 3rd-party solution that allows you to embed a provider’s iPaaS into your platform.

The platform typically provides multiple deployment options. For instance, you can either build the integrations on behalf of clients or allow them to do so within your platform.

[![A visual representation of an embedded iPaaS](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c800f6636838057079bb24_fDzCBNbPLhd3K7XnzjhzqGZbGtROnV4h7JyymDtXdYiB45FcJ7s_jcLeP5M2uKcX-28w0QMbcI2MtVe2U-_eRP6JQ9nxS1EQXDvZ35ROpwNCnz28zd48rTFD-4cpyXFmVOD1cf-J30f4fu5_Sd6GFLs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c800f6636838057079bb24_fDzCBNbPLhd3K7XnzjhzqGZbGtROnV4h7JyymDtXdYiB45FcJ7s_jcLeP5M2uKcX-28w0QMbcI2MtVe2U-_eRP6JQ9nxS1EQXDvZ35ROpwNCnz28zd48rTFD-4cpyXFmVOD1cf-J30f4fu5_Sd6GFLs.webp)

‍

And while embedded iPaaS solutions are a step in the right direction, they don’t fully address the issues presented in in-house development.

They still require a significant amount of technical expertise to use—ultimately forcing your engineers (or your clients) to build and manage the integrations. In addition, you’ll only be able to build one integration at a time, making the prospect of launching a high-volume of integrations quickly all but impossible. Lastly, you will have to maintain these integrations in a new no-code tool where your engineers are less familiar and comfortable with making quick changes.

_Related:_ [_How to decide between an Embedded iPaaS and a unified API_](https://merge.dev/blog/embedded-ipaas-vs-unified-api)

### **Unified API solution**

Unified APIs are the newest generation of integrations providers, and emerged in popularity in the early 2020s. A [unified API platform](https://merge.dev/blog/what-is-a-unified-api) is a 3rd-party solution that offers a suite of aggregated APIs; each aggregated—or unified—API allows you to connect to multiple 3rd-party solutions in a given software category, such as a CRM.

[![A visual representation of a unified API platform](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c800f780703460354fbe5b_OXoHHcLWwylRi0lmS2vjAjbA7e2SMuZ3rcGoExrwrKIVrRXR3eal9WRh2DKfKuT-ZYbWxLXK5myOZsQLOMjwuSTusyQ9PPNoSbkUggY6uZT4eOmgNmbVYuz_GDUkMmH-JHJkZWFOILtYI8lWs0cl-BQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c800f780703460354fbe5b_OXoHHcLWwylRi0lmS2vjAjbA7e2SMuZ3rcGoExrwrKIVrRXR3eal9WRh2DKfKuT-ZYbWxLXK5myOZsQLOMjwuSTusyQ9PPNoSbkUggY6uZT4eOmgNmbVYuz_GDUkMmH-JHJkZWFOILtYI8lWs0cl-BQ.webp)

‍

This type of platform neatly addresses the drawbacks presented in the other options: namely, you can integrate at scale with minimal effort. For instance, Merge lets you connect to more than 40 ATS vendors by simply connecting to its [ATS Unified API](https://merge.dev/categories/ats-recruiting-api).

But Merge goes beyond other unified API platforms in a number of other ways.

We offer 7 unified APIs (and growing) to ensure you’re able to scale any type of integration; we provide comprehensive common models across our unified APIs, in addition to features that allow you to access custom fields and objects; we have out-of-the-box [integrations management capabilities](https://merge.dev/features/integrations-management) to help your team assess clients’ integration activities and health as well as assist end-users on resolving their integration issues.

Merge also allows customizability outside of our normalized data, including custom fields, custom objects, pass-through requests, and overriding their existing data models. These features allow you to gain the benefit of one to many, while retaining customizability for enterprise and custom use cases.

## Getting started with ATS APIs

In addition to understanding ATS API structures, you’ll also want to keep in mind a few additional topics as you start building:

- API format - REST, SOAP, etc.
- Authentication
- Pagination
- [Rate Limits](https://www.merge.dev/blog/what-is-api-rate-limiting)
- Test Accounts

Integrating with multiple ATS systems? Merge unified multiple ATS APIs into one, making it easy to integrate your app with every ATS that your customers use. The [Unified ATS API](https://www.merge.dev/categories-old/ats-recruiting-api) is REST-based, with normalized authentication, pagination, and rate limiting. Merge's dashboard also includes detailed logging and issue detection to make integration management painless. Hundreds of companies use Merge to power their ATS APIs, including Gong, Calendly, and Ripplematch.

To learn more about Merge, you can [schedule a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-ats-api-integrations).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)

Shensi Ding

CEO and co-founder

@Merge

## Read more

[Software scalability: design, strategies and best practices](https://www.merge.dev/blog/software-scalability)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)

### Software scalability: design, strategies and best practices

Insights

[How to integrate with the SharePoint API via Python](https://www.merge.dev/blog/sharepoint-api-python)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b2d1e5322f98bcf08952_Blog%20Header%20Brand%20Refresh%20(1).jpg)

### How to integrate with the SharePoint API via Python

Engineering

[How to build integrations for AI agents](https://www.merge.dev/blog/ai-agent-integrations)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)

### How to build integrations for AI agents

AI

## Subscribe to the Merge Blog

Get stories from Merge straight to your inbox

[Subscribe](https://www.merge.dev/get-in-touch?utm_btn=dr-page-root)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67a0696c88fcb6b1a1d8ad6f_CTA%20Background%20Logo.svg)

### Get our best content every week

Our weekly newsletter provides the best practices you need to build high performing product integrations.

Your email

Thank you! Your submission has been received!

Oops! Something went wrong while submitting the form.

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d8d0a062-d14c-457f-9566-fce82997136b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f4659e4e-7d9b-43c3-af30-ca1d4d9932f5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-ats-api-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d8d0a062-d14c-457f-9566-fce82997136b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f4659e4e-7d9b-43c3-af30-ca1d4d9932f5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-ats-api-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=a7e0b946-2d81-42fc-8daa-3a4e1aa9a8e0&bo=2&sid=54e2cf103e8e11f0b59b61d849169f87&vid=54e2f6d03e8e11f09c6ee768a7911e57&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=ATS%20integration%3A%20definition,%20examples,%20and%20tools&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-ats-api-integrations&r=&lt=752&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=973901)