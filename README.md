# Travel Agent: An Interactive AI-Powered Map Application

## Description
Travel Agent is an interactive web application designed to enhance the experience of planning trips and exploring locations. Built with Streamlit and integrated with OpenAI's GPT model, this app offers real-time conversational AI capabilities coupled with dynamic map visualization. Users can interact with the AI to get travel advice, find locations, and see these locations plotted on a map in real time.

## Features
* AI-Powered Conversations: Engage with an AI assistant for  travel-related queries.
* Dynamic Map Visualization: See your travel destinations come to life on an interactive map.
* Real-Time Updates: Map markers and views update based on the conversation with the AI.
* User-Friendly Interface: Simple and intuitive design for easy navigation.


## Install Dependencies:

* pip install -r requirements.txt
* Set Up OpenAI and Mapbox Tokens:

# Obtain an API key from OpenAI.
Get a Mapbox access token for map functionalities.
Create a secrets.toml file in your Streamlit directory and add your OpenAI API key and Mapbox token.
Run the Application:

* streamlit run app.py

# Usage
After launching the app, you can start interacting with the AI assistant through the chat input. Ask questions or request information about travel destinations. The map on the right will update based on the AI's responses, showing locations, points of interest, or travel routes.

# Technologies
* Streamlit: For creating the web application.
* OpenAI's GPT: Powers the conversational AI.
* Plotly: For dynamic map visualization.
* Python: The primary programming language used.
Contributing
* Contributions to the Travel Agent app are welcome.

Also add the following functions in your assistant: 

```
{
  "name": "update_map",
  "description": "Update map to center on a particular location",
  "parameters": {
    "type": "object",
    "properties": {
      "longitude": {
        "type": "number",
        "description": "Longitude of the location to center the map on"
      },
      "latitude": {
        "type": "number",
        "description": "Latitude of the location to center the map on"
      },
      "zoom": {
        "type": "integer",
        "description": "Zoom level of the map"
      }
    },
    "required": [
      "longitude",
      "latitude",
      "zoom"
    ]
  }
}
```

```
{
  "name": "add_markers",
  "description": "Add list of markers to the map",
  "parameters": {
    "type": "object",
    "properties": {
      "longitudes": {
        "type": "array",
        "items": {
          "type": "number"
        },
        "description": "List of longitude of the location to each marker"
      },
      "latitudes": {
        "type": "array",
        "items": {
          "type": "number"
        },
        "description": "List of latitude of the location to each marker"
      },
      "labels": {
        "type": "array",
        "items": {
          "type": "string"
        },
        "description": "List of text to display on the location of each marker"
      }
    },
    "required": [
      "longitudes",
      "latitudes",
      "labels"
    ]
  }
}
```