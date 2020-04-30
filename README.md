# DynamoAdjacencyAnalysis
This Dynamo script is designed for checking distances from one type of programmatic element to another.  The initial inspiration for this script was checking the distance to the nearest equipment storage closet for a set of patient rooms.  Using project parameters, custom groupings of rooms can be selected as start points or destinations, and paths of travel will be drawn from the center point of each starting room to the center point of each destination room.  The distance from the shortest path of travel will be logged in a custom parameter for each starting room, allowing for visualization and / or scheduling. 

## Requirements ##
The script in this folder was written for Revit 2020, and will not work in earlier versions.  The UI elements of the script were built with the Data Shapes package, and require this package to be installed before running the script.

## Instructions ##

1. Verify the appropriate Dynamo Packages have been installed and that your Revit version is 2020 or later.
2. Open a Revit model that has reached a minimum point of development where it has rooms, walls and doors.
3. Add a text type project parameter to the rooms.  This parameter will be used to classify which are starting points and which are destinations.  The parameter can be named whatever you like, but should be instance based and allowed to vary between groups.
4. Add a number type project parameter to the rooms.  This parameter will be used to store the analysis results each time the script is run.  This number will be set only for the starting rooms, and will contain only the distance to the nearest destination.
5. Verify that the Path of Travel parameters are appropriate for the view where the analysis will be taking place.  If there is too much furniture or other complex geometry being included in the analysis, it can take an extremely long time to run, even for a small view.  These settings can be adjusted by clicking the drop-down arrow on the Route Analysis Menu of the Analyze tab in Revit.
6. Press play in the Dynamo Player, and the following dialog box will appear.  Use the two drop down menus to select the parameters created in steps 3 and 4.  Click the Select Parameters button when these have been set.
7. A second dialog box will appear that reads the existing values of the Analysis Code parameter (if no parameters have been set, this may result in an error) and allows the user to select parameters for starting and ending locations.  Two check boxes provide an extra level of control.  If this analysis is meant to replace a previous result, checking the Delete Existing Travel Paths button will delete all travel paths visible in the view before running the analysis.  If the Shortest Paths button is checked, only the shortest path from each Start Room to the nearest Destination Room will be drawn.
