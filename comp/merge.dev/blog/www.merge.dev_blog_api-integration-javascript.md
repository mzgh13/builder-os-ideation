---
url: "https://www.merge.dev/blog/api-integration-javascript"
title: "How to integrate with the BambooHR API using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-integration-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-integration-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-integration-javascript#)

Table of contents

[How to perform API integration in JavaScript with BambooHR](https://www.merge.dev/blog/api-integration-javascript#how-to-perform-api-integration-in-javascript-with-bamboohr)

[API integration maintenance](https://www.merge.dev/blog/api-integration-javascript#api-integration-maintenance)

[Conclusion](https://www.merge.dev/blog/api-integration-javascript#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-javascript)

##### Just for you

No items found.

# How to integrate with the BambooHR API using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Lucien Chemaly

@Merge

Application programming interfaces (APIs) are the building blocks of modern software, allowing different applications to communicate with each other. And if you're learning JavaScript, you've probably come across the term [_API integration_](https://www.merge.dev/blog/api-integration), which refers to the process of linking one application to another via their APIs.

To help you understand how API integration works, this tutorial will show you how to integrate with an API in JavaScript, focusing on the [BambooHR Applicant Tracking System (ATS) API](https://documentation.bamboohr.com/).

## How to perform API integration in JavaScript with BambooHR

In this tutorial, you'll learn how to integrate your React application with BambooHR APIs to access HR-related data. You'll set up a [React](https://react.dev/) project, create pages to display and create candidate data, and even explore the underlying network calls. By the end, you'll have a working app that interacts with the BambooHR API.

### Prerequisites

Before getting started, make sure you have the following installed:

- [**Node.js**](https://nodejs.org/en) **and** [**npm**](https://www.npmjs.com/) **:** Make sure these are [downloaded and installed](https://nodejs.org/en/download/) on your machine.
- **A text editor:** You can use any text editor; however, [Visual Studio Code](https://code.visualstudio.com/) is recommended for its robust JavaScript and React support.

Once Node.js is set up, it's time to create a new React project. To do so, execute the following commands in your terminal: `npx create-react-app bamboohr-appcd bamboohr-app`

This creates a new React application and navigates you into the project folder.

Next, you need to install a package to manage HTTP requests. You'll use [Axios](https://axios-http.com/) and [Material UI](https://mui.com/) as the UI components. To install these libraries and their dependencies, open your terminal or shell and run the following:

```python

npm install axiosnpm install @mui/material @emotion/react @emotion/styled

```

‍

_Related:_ [_What is API integration management? Here's everything you need to know_](https://www.merge.dev/blog/api-integration-management)

### Explore the BambooHR API documentation

Before writing any code, it's crucial that you understand the API you're working with. For BambooHR, you'll find extensive documentation on their [official website](https://documentation.bamboohr.com/reference/get-employee). The two types of APIs you'll focus on are as follows:

- [**Data Access API**](https://documentation.bamboohr.com/reference/get-applications-1) for retrieving candidates'/applicants' data.
- [**Data Manipulation API**](https://documentation.bamboohr.com/reference/get-applications-1) for creating new candidates/applicants.

Each of these APIs has specific endpoints you'll call from your app. For this tutorial, you'll use the following:

- **Data Access API endpoint:** /v1/applicant\_tracking/applications/jobs
- **Data Manipulation API endpoint:** /v1/applicant\_tracking/applications

### Generate your BambooHR API Key

BambooHR offers several types of authentication, such as API key–based and OAuth. For simplicity, API key–based authentication is used here.

To generate your BambooHR key, start by signing up for a [free BambooHR demo account](https://www.bamboohr.com/demo):

[![BambooHR sign-up](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d42347e6d0d569647c9db_D7vE76l.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d42347e6d0d569647c9db_D7vE76l.webp)

Once you're logged into your account, click on your profile icon and select **API Keys**:

[![BambooHR API Keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d4235d116b7816504644d_o5QqUW5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d4235d116b7816504644d_o5QqUW5.webp)

Click on **Add New Key**, name your key react-app-key, and click on **Generate Key**:

[![Generate BambooHR API Key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d423425c74b53c0929144_wYlfnFt.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d423425c74b53c0929144_wYlfnFt.webp)

Select the **COPY KEY** button to copy the key and store it somewhere safe as you'll need it later in your React application. Then click on **Done** to close the dialog:

[![BambooHR API Key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d42340e9d7a98068ffd07_Ur8lEgu.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652d42340e9d7a98068ffd07_Ur8lEgu.webp)

_Related:_ [_How to test API integrations_](https://www.merge.dev/blog/api-integration-testing)

### Set up a proxy

Setting up a proxy in a React application, especially one created using the [Create React App (CRA)](https://create-react-app.dev/), is straightforward. The proxy helps you resolve [cross-origin resource sharing (CORS)](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) issues during development.

In the root of your React project, find your package.json file. This file should be at the same level as your node\_modules folder and src folder.

In the package.json file, add a new key called proxy and set its value to the URL of the API you're trying to connect to. Make sure to add this key-value pair at the top level of your JSON object, not inside any other nested objects: `{  "name": "bamboohr-app,  "version": "0.1.0",  "private": true,  "proxy": "https://api.bamboohr.com",  ...code omitted…}`

In this case, the proxy is set to https://api.bamboohr.com, which is the base URL for the BambooHR API. Now, when you make API calls in your React app, you don't have to include the full URL of the API; just include the path, and the proxy setting automatically prepends the base URL.

The React development server automatically routes the requests through the proxy, avoiding the CORS issue.

**Please note:** This is intended for development purposes only. In production, you'd want to handle CORS issues on your server, not by using a client-side proxy.

### Display candidate information from BambooHR

To display candidate information from BambooHR, create a new file called Candidates.js inside the src folder and add the following:

```javascript

import React, { useState, useEffect } from "react";
import axios from "axios";
import {
  List,
  ListItem,
  ListItemText,
  Dialog,
  DialogTitle,
  DialogContent,
  Avatar,
} from "@mui/material";

const Candidates = ({ candidates, setCandidates }) => {
  const [open, setOpen] = useState(false);
  const [selectedCandidate, setSelectedCandidate] = useState(null);

  const handleClickOpen = (candidate) => {
    setSelectedCandidate(candidate);
    setOpen(true);
  };

  const handleClose = () => {
    setOpen(false);
  };

  useEffect(() => {
    const fetchData = async () => {
      const result = await axios.get(
        "/api/gateway.php/your-subdomain/v1/applicant_tracking/applications",
        {
          headers: {
            Authorization: `Basic ${btoa(
              "your-api-key:password"
            )}`,
            Accept: "application/json",
          },
        }
      );

      setCandidates(result.data.applications);
    };

    fetchData();
  }, []);

  return (

      Candidate List

        {candidates?.map((candidate, index) => (
           handleClickOpen(candidate)}
          >


            {candidate.status.label}

        ))}




          {selectedCandidate?.applicant.firstName}{" "}
          {selectedCandidate?.applicant.lastName}


          {selectedCandidate?.job.title.label}



  );
};

export default Candidates;

```

Here, you define a React component called Candidates to display a list of job candidates. The useState and useEffect hooks are utilized for managing state and fetching data from an API, respectively. The component uses Material UI to display a list of candidates, each of which can be clicked to open a dialog box showing more details. The handleClickOpen function sets the selected candidate and opens the dialog, while handleClose closes it. The useEffect hook fetches candidate data when the component mounts and populates the candidates state through the setCandidates function passed as a prop.

Make sure you replace your-subdomain with your BambooHR subdomain and 'your-api-key' with the API key you generated. You can keep the password as is or input any random text.

### Create a page to add new candidates

To create a page where you can add new candidates, you need to create a new file called AddCandidate.js inside the src folder and add the following code:

```javascript

import React, { useEffect, useState } from "react";
import axios from "axios";
import {
  Button,
  TextField,
  Dialog,
  DialogActions,
  DialogContent,
  DialogTitle,
  FormControl,
  InputLabel,
  Select,
  MenuItem,
} from "@mui/material";

const AddCandidate = ({ setCandidates }) => {
    const [open, setOpen] = useState(false);
    const [jobs, setJobs] = useState([]);
    const [selectedJob, setSelectedJob] = useState({});
    const [formData, setFormData] = useState({
        firstName: "",
        lastName: "",
        jobId: "",
    });

    const handleClickOpen = () => {
        setOpen(true);
    };

    const handleClose = () => {
        setOpen(false);
    };

    const handleChange = (e) => {
        console.log(e.target, 'selected job');
        const { name, value } = e.target;
        setFormData({ ...formData, [name]: value });
    };

    const updateSelectedJob = (job) => {
        console.log(job, "job");
        setSelectedJob(job);
    }
    const handleSubmit = async (e) => {
        e.preventDefault();
        try {
            const result = await axios.post(
            "/api/gateway.php/your-subdomain/v1/applicant_tracking/application",
            formData,
            {
                headers: {
                Authorization: `Basic ${btoa(
                    "your-api-key:password"
                )}`,
                "Content-Type": "application/json",
                },
            }
            );

            if (result.status === 200) {
                setCandidates((prevCandidates) => [\
                  ...prevCandidates,\
                  {\
                    appliedDate: new Date(),\
                    status: {\
                      id: 1,\
                      label: "New",\
                    },\
                    rating: null,\
                    applicant: {\
                      firstName: formData.firstName,\
                      lastName: formData.lastName,\
                      avatar: "",\
                      email: "",\
                    },\
                    job: {\
                      id: selectedJob.id,\
                      title: {\
                        id: null,\
                        label: selectedJob.title.label,\
                      },\
                    },\
                  },\
                ]);
            }
        } catch (error) {
            alert("Failed to add a new candidate.");
        }
        handleClose();
    };

    useEffect(() => {
        const fetchJobs = async () => {
        try {
            const result = await axios.get(
            "/api/gateway.php/your-subdomain/v1/applicant_tracking/jobs",
            {
                headers: {
                Authorization: `Basic ${btoa(
                    "your-api-key:password"
                )}`,
                Accept: "application/json",
                },
            }
            );
            setJobs(result.data);
        } catch (error) {
            console.error("An error occurred while fetching the jobs: ", error);
        }
        };
        fetchJobs();
    }, []);

  return (


        Add Candidate


        Add a New Candidate




            Job

              {jobs.map((job, index) => (
                 updateSelectedJob(job)}
                >
                  {job.title.label} - {job.location.label}

              ))}





            Cancel


            Add




  );
};

export default AddCandidate;

```

In this code, you create a React component named AddCandidate that allows users to add new job candidates. It uses React hooks like useState and useEffect for state management and API calls, respectively.

The UI relies on Material UI components to render a dialog box that contains a form. Within this form, users can enter first and last names and choose a job from a drop-down. Upon submission, the handleSubmit function makes an API POST request to add the new candidate and updates the parent component's state.

Again, make sure to replace your-subdomain with your BambooHR subdomain and 'your-api-key' with the API key you generated.

### Create a Candidate Container

Now, you need to create a container that acts as a parent component for the components you previously created. This lets you share the candidate's list between these two components.

Create a new file called CandidateContainer.js inside the src folder and add the following code:

```javascript

import React, { useState } from "react";
import AddCandidate from "./AddCandidate";
import Candidates from "./Candidates";
import Container from "@mui/material/Container";
const CandidateContainer = () => {
  const [candidates, setCandidates] = useState([]);
  return (




  );
};
export default CandidateContainer;

```

Here, you define a CandidateContainer React component that serves as the parent component for Candidates and AddCandidate. It maintains the state for the list of candidates through the candidates and setCandidates state variables. Both child components receive candidates and setCandidates as props, allowing them to read and modify the candidate list. The Material UI Container component is used for layout styling.

Next, open your App.js file and update the code to look like this:

```javascript

import './App.css';
import CandidateContainer from './CandidateContainer';

function App() {
  return (



  );
}

export default App;

```

Here, you set up the root App component for your React application. It simply imports and renders the CandidateContainer component, making it the central content of the app.

### Run and Test the Application

Open your terminal or shell, go to the root directory of your application, and run the following command, which runs your application: `npm start`

All the code for this tutorial is available in [this GitHub repo](https://github.com/See4Devs/reactjs-bamboohr-integration).

_Related:_ [_An overview on the API integration process_](https://www.merge.dev/blog/api-integration-process)

## API integration maintenance

Managing the integration with third-party APIs like BambooHR or other platforms can be tricky and time-consuming. You have to worry about API endpoints changing, new authentication schemes being introduced, and rate limits being altered. Each of these changes requires that you dive back into your code to make adjustments, which is time-consuming and diverts your focus from building features that add direct value to your application.

Unified APIs like Merge offer a way to streamline this aspect of your development workflow. Instead of interacting with multiple disparate APIs, you can interact with one unified interface. Behind the scenes, Merge takes care of routing your requests to the appropriate service and handles any peculiarities or updates in those individual APIs. This means you don't have to constantly monitor changes to every API you integrate; Merge does that for you.

## Conclusion

In this article, you learned how to integrate with the BambooHR API using JavaScript and React. You explored both Data Access and Data Manipulation APIs, writing network calls to fetch and add candidates.

However, keep in mind that API integration is a complex and evolving field. If you want to eliminate the complexities and hassles of keeping up with API changes, consider using a [unified API solution](https://www.merge.dev/blog/what-is-a-unified-api) like Merge.

Simply build once to Merge's Unified API and get access to hundreds of integrations across key  software categories—from HRIS to ATS to file storage to CRM.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-javascript) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Lucien Chemaly

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

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

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