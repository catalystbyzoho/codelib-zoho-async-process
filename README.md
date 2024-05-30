# Zoho Async Process

##  **Introduction**

The Zoho Async Process CodeLib aids in transforming synchronous requests into asynchronous ones, enhancing application performance and responsiveness.

## **Components Used in Catalyst**

- Catalyst Serverless Functions
    - custom_event - This is an event function, which helps in processing the data.

- Catalyst Cloud Scale Event Listener
    - Event listener(**CustomEventQueue**) and rule(**slack_app**) will be automatically created and linked to the target event function(**custom_event**)


## **How to use**

### **Configuring Catalyst**

Before installing any Catalyst CodeLib solution, please make sure to login to the Catalyst CLI using your Catalyst account by following the steps mentioned [here](https://docs.catalyst.zoho.com/en/cli/v1/cli-command-reference/).

Follow all the steps mentioned below to install, configure and execute the Zoho CRM Streaming Agent CodeLib.

#### **Step 1: Install the CodeLib solution**

If you are installing the CodeLib solution for an already existing Catalyst project, navigate to its root directory from your terminal and directly proceed with installing the CodeLib.

You can also initialize a new project following the steps mentioned in this page. After you initialize the project, proceed to navigate to its root directory and continue with the installation.

Execute the command below in the terminal to install the Zoho Async Process CodeLib solution:

```bash
catalyst codelib:install https://github.com/akilavan-jayakumar/codelib-zoho-async-process
```

Upon installation, the pre-configured Catalyst resources of the CodeLib solution will be automatically deployed to the Catalyst console.

#### **Step 2: Configure Functions Component**

1. Open the `functions` directory of your Catalyst project in your local system.
2. In the index.js file for the `custom_event` function, include your logic for processing data.

After completing the configuration changes as instructed, proceed to deploy the CodeLib solution again from your local terminal. This ensures that the modifications are applied and visible in the remote console.

#### **Step 3: Execute Catalyst Catalyst Cloud Scale Event Listener Produce Url**

You can either execute the cURL command listed below in the terminal directly or incorporate the function endpoint in your application logic to handle any synchronous requests.

```bash
curl --location --request POST '{{PRODUCE_URL}}' \
--header 'Content-Type: application/json' \
--data '{
    "rule_identifier":"slack_app",
    "data":{{YOUR_DATA}}
}'
```

To obtain the `PRODUCE_URL`, navigate to the Catalyst Console, select the relevant project, then proceed to CloudScale Service -\> Event Listener -\> Click on `CustomEventQueue`. In the overview section, you will find the produce url.
