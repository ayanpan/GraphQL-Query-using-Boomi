# GraphQL-Query-using-Boomi

## Generate Query Request Payload using Postman
GraphQL Query can be tricky to directly write in Boomi process canvas. I recommend using Postman to generate the same with the following steps.

**Step-1:** Send the request payload by clicking the **Send** button on the top-right corner, as per the below screenshot, so that we can generate the response.

![a0](https://user-images.githubusercontent.com/12267939/205017655-5fe1ba42-3380-4e8c-b502-102b46cb6d71.JPG)

**Step-2:** View code by clicking the **</>** symbol on the right side, as per the below screenshot.

![a1](https://user-images.githubusercontent.com/12267939/205017951-1220196d-cd33-4b00-9850-46c0805ae8de.JPG)

**Step-3:** Select **HTTP** from the dropdown-list, and copy the contents of **Line#6**, as per the below screenshot.

![a2](https://user-images.githubusercontent.com/12267939/205018749-2987d9aa-c36c-4f67-b2a5-a53f730e0cf1.JPG)



## Call GraphQL API using Boomi
Overall Boomi process is as below.

![a3](https://user-images.githubusercontent.com/12267939/205021012-5bf1e7c5-b86d-451c-92a8-ccf6a852c1d7.JPG)

**Step-1:** Paste the contents copied in **Step-3:** of **Generate Query Request Payload using Postman** in the Message shape. The "variables" element can be removed as we are not using it.

![a4](https://user-images.githubusercontent.com/12267939/205024715-2c775a9a-c5ba-4b4c-b73d-6870f1eb6d38.JPG)

**Step-2:** Configure the URL in HTTP Client connection.

![a5](https://user-images.githubusercontent.com/12267939/205024773-c0be81cb-0aaf-452d-b6b2-00de2b502cd7.JPG)

**Step-3:** Configure the HTTP Client operation, as per the below screesnhot.

![a6](https://user-images.githubusercontent.com/12267939/205024825-d33d6861-1658-424e-9a5a-cb7668029ab7.JPG)

**Step-4:** Use Decision shape to segregate success and error response.

![a7](https://user-images.githubusercontent.com/12267939/205024916-db36d68c-548e-46a3-9688-98b8ebe1f5d1.JPG)

**Step-4:** Configure the Map shape, as per the below screenshot, or, as per the project requirement.

![a8](https://user-images.githubusercontent.com/12267939/205025009-6d86de24-fac0-4dca-b0a9-b37ca0d3cf63.JPG)

**Step-5:** Configure the Notify shape, as per the below screenshot, or, have the error handling mechanism as per the project requirement.

![a9](https://user-images.githubusercontent.com/12267939/205025049-d688b0be-0b0c-418f-aa3d-43288e002d35.JPG)



## Process Execution Details
Below are the screenshots of successful process execution and response from GraphQL API.

![a10](https://user-images.githubusercontent.com/12267939/205025589-60fcda1d-d017-4aa0-93c2-7fb7f6f3c84e.JPG)

![a11](https://user-images.githubusercontent.com/12267939/205025630-bea1bc14-fa65-4df9-bdff-0289ea374ed3.JPG)

![a12](https://user-images.githubusercontent.com/12267939/205025662-5b8136aa-fcef-45b4-b64b-ae66526bc8a4.JPG)

![a13](https://user-images.githubusercontent.com/12267939/205025699-3d139b49-845c-41d3-aaf0-4dcda86aa041.JPG)


## Sample API and Document Details

I've used an API from this website - https://www.apollographql.com/blog/community/backend/8-free-to-use-graphql-apis-for-your-projects-and-demos/.

**URL:** https://countries.trevorblades.com/graphql

**HTTP Method:** POST

**Query:** 

'{"query":"query Query {\r\n  country(code: \"IN\") {\r\n    name\r\n    native\r\n    capital\r\n    currency\r\n    languages {\r\n      code\r\n      name\r\n    }\r\n  }\r\n}"}'

**Response:** 

{
    "data": {
        "country": {
            "name": "India",
            "native": "भारत",
            "capital": "New Delhi",
            "currency": "INR",
            "languages": [
                {
                    "code": "hi",
                    "name": "Hindi"
                },
                {
                    "code": "en",
                    "name": "English"
                }
            ]
        }
    }
}
