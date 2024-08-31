# Project Setup Instructions

This guide will help you set up your environment to synchronize Trello tasks with Google Calendar using a Python script. Before you begin, ensure you have minimal Python experience and understand what API keys are and how they are used.
If you have any questions or ideas about product development, reach out to me in the issues section.

## Setup Instructions

### Step 1: Trello Configuration
1. **Create a Trello Board**: Set up a board in Trello with a list of tasks you want to update and use in Google Calendar.
3. **Add Any Fields Power-up**: Set up Any Fields power-up. Just connect it to atlassan account for global. This time I've used v1.3.1
2. **Add a Custom Field**: In Any Fields, add a field for example "estimate" (name is not important). Type must be "Number". Check "show on card front" checkbox. Use [official guide](https://schnapps.tech/products/trello-power-ups/any-fields/fields)
3. **Generate API Key and Token**: Obtain your Trello API key and token by following the instructions [here](https://developer.atlassian.com/cloud/trello/guides/rest-api/api-introduction/).
4. **Identify Board and List ID**: Find your Board ID and List ID in Trello.

### Step 2: Google Calendar Configuration
1. **Enable Google Calendar API**: Visit Google Cloud Console, enable the Google Calendar API, and create OAuth API ID credentials with the Desktop API type. Ensure to enable developer mode to avoid the need for review in production mode.
2. **JSON Credentials**: Store the JSON file with your credentials in the application folder.
3. **Create a Separate Google Calendar**: This calendar will store the tasks as events. Note: the current script clears the calendar each time it's executed, so avoid storing other important events in this calendar.

### Step 3: Environment Setup
0. **You can find LIST_ID** in *board menu > Print, export, and share > json > ctrl+f > type lists > seek for id*
1. **Environment File**: Create a `.env` file in your project root and add the following keys:
   ```
   CALENDAR_MAIN_ID=your-main-calendar-id
   CALENDAR_TASKS_ID=your-tasks-calendar-id
   API_KEY=your-trello-api-key
   TOKEN=your-trello-token
   LIST_ID=your-trello-list-id
   ```
   ~~ESTIMATE_FIELD_ID=your-trello-custom-field-id~~ now useless

### Step 4: Running the Script
1. **Execute the Script**: Run the Python script. During the first run, it will show a URL to connect to the Google Calendar API.
2. **Authorization**: After granting access, the page will likely return an error. Copy the "code" value shown on the error page and enter it into the application as instructed by the script.

**Note**: This script is a personal draft and requires customization. An easy-to-use version will be developed later.

## Result
### Initial state
<img src="media/image-4.png" alt="alt text" width="250" height="w">

![](media/image-3.png)
<!-- <img src="media/image-3.png" alt="alt text"  height="350"> -->

### Script performed
<img src="media/image-7.png" alt="alt text" width="250" height="w">

![](media/image-8.png)
<!-- <img src="media/image-8.png" alt="alt text" width="w" height="350"> -->
