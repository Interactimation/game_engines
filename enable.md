---
layout: page
title: Enable Functions
---

# Enable Functionality

Jan has settings which can enable it to 
* Search the web
* "Fetch" items to present to your models
* Give the model permission to read from and write to to a specific folder on your device

## Enable Web Access

* Click Settings
* Under INTEGRATIONS, click MCP Servers
* Turn ON Jan Browser MCP —if it's not on

## Enable Fetch

* Click Settings
* Under INTEGRATIONS, click MCP Servers
* Turn ON Fetc —if it's not on

## Enable Read / Write

* First, create a special folder, just for Jan —don't keep anything in it but documents you want your models to read or write
* Copy the "path" to this folder:
    * **Windows:** Right-click the folder and select Copy as path
    * **Mac:** Select the folder in Finder and press Option + Command + C
* In Jan, Click Settings
* Under INTEGRATIONS, click MCP Servers
* Find Filesystem —_before turning it on_, use the pencil icon to edit it
* Under arguments you may find something that looks like a dummy of your folder path —replace it with your folder path (if you don't see anything like that, click the + sign beside Arguments and paste your path into the new field)
* Turn on Filesystem

## Test All the Above

* Open a new conversation and prompt:

   ```text
   Using the Filesystem MCP, create a File named hello-world.md in the authorized folder

   Write in the document exactly: # Hello, World!
   ## This Markdown File was created by my local Model in Jan.

   Do not write anywhere else. Tell me the complete path of the File you created.
   ```

* Check the proposed tool action and approve it. Open `hello-world.md` from the folder and confirm that its contents are correct.

> **CONSIDER:** You are authorizing the **Filesystem MCP**, not giving the Model unrestricted access to your computer. The Model should be able to write only within folders allowed through the Filesystem MCP
