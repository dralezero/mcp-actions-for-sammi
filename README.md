# Elgato MCP Controller Deck for SAMMI  
A SAMMI deck of buttons to request and trigger Stream Deck actions through Elgato MCP server  

## Setup Stream Deck:

Stream Deck 7.4.0 or higher  
   Settings > General > Enable MCP Actions

   Put actions in profile: MCP Actions

   Give each action a unique title
   Tested format: TITLE_LIKE_THIS

   Right click actions to trigger and test

## Setup Elgato MCP Server  

### Auto install:  
   install-nodejs-elgatomcp.bat  
   Right-click Run as Administrator  

### Manual install  
   Tutorial: https://www.youtube.com/watch?v=6fAbno8UpZU
   
   Install: Node.js  
   https://nodejs.org/en  
   Do not need to check "Automatically install the necessary tools"  

   Open PowerShell as administrator
   run:  
   npm install -g @elgato/mcp-server  

   If script execution policy error:  
   run:  
   Set-ExecutionPolicy RemoteSigned  

   Can set back to default after:  
   Set-ExecutionPolicy Restricted

More info: https://www.elgato.com/ww/en/explorer/products/stream-deck/sd-mcp-setup/

## SAMMI Tutorial
https://www.youtube.com/watch?v=B_b3dzYnsts

### Configuration:
Open default variables for ELGATO_MCP_CONFIG
Edit the "elgato_mcp_url" value as needed for your setup.
Default is "http://localhost:9090/mcp"

Edit Elgato MCP Server Start and Stop buttons for the file paths to:  
elgato_mcp_start.bat  
elgato_mcp_stop.bat  

## How to use:  

### Elgato MCP Start Server  

   Recommend add Trigger to run when SAMMI Startup or start stream
   This will open bat file to start server  
   a blank cmd window will open minimized (this is launched as another cmd from the .bat which exits immediately)  
   it needs remain open to keep mcp server running  
   Then it will trigger the button Elgato MCP Data to get session ID and list of actions  

### Elgato MCP Data  

   Gets MCP session ID from server and pulls list of MCP Actions from Stream Deck  
   Session idle timeout after 1 hour of no requests  
   Keep alive: Add Repeat Interval 45 minutes: 2700000 ms  

### For each Stream Deck MCP Action  

   (Suggest creating a 32 button deck for MCP Actions as Stream Deck MCP provides a 32 key page)  
   
   Copy SAMMI button "Elgato MCP Action Template"  

   Rename as desired  

   Open the button and replace "BUTTON_TITLE" with MCP Action title  

   Add desired trigger or trigger from another SAMMI button  

### Elgato MCP Stop Server:  

   Recommend add Trigger to run when SAMMI Shutdown or end stream
   The .bat script will kill the task running on the port 9090 which is Elgato MCP server  

## Credit

Deck and buttons created by DraleZero with and for SAMMI  
Free to use and modify for personal use.  
Do not sell or redistribute without permission.  

## Disclaimer  

This is an unofficial community project. I am not affiliated with  
SAMMI Solutions or Elgato or any of their products. All product names, logos,  
and brands are property of their respective owners.  
