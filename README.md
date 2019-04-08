# Pubbly design tools

A livecode cross platform application to create pubbly brand export files

## Getting Started

### Designers

To start using the pubbly design tools to create content, download the windows or Mac packages, extract or install, and launch the application.

Pubbly can also work on a linux machine through Wine, but this is mostly untested.

For help on how to create content, read through the applications built in help menu, specifically the Terms and Concepts.

### Developers

To start editing the source code of the Pubbly Design Tools, first download a copy of [LiveCode Community 7.1.4](https://downloads.livecode.com/livecode/). Download and unzip the Window.zip package, and rename the file Tools.pbly to Tools.livecode. Open the Tools file from within Livecode.

Changes must be done from within the Livecode IDE.

## Creating books

A full help section is available inside the design tools them selves. Please refer to help -> Terms and Concepts

## Exporting books to a console

For a full explanation of each of the four pubbly console exports, see [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section Exports. As a quick overview,

* Static exports: Created from Design tools. "As is".
* Variable exports: Created from Design tools. Templated and mass produced on console.
* Stitched exports: Created from above two exports on console CMS. Collection of pages from number of different sources
* Map exports: Multiple interconnected exports tied together with URL links, downloaded as a fully connected package (for APK, offline, or serverside deployment).

Every export has as associated XML file. If you plug that XML file into the Pubbly Engine, it can run online, offline, or wrapped in a cordova created APK. Instructions for how to do that are at [Pubbly Engine](https://github.com/PubblyDevelopment/pubbly_engine) section building from xml.

For a more project friendly approach, use a pubbly console.

### Getting a console

To build a console from scratch, follow instructions at [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Getting Started". This will allow you complete control over the environment.

To "try out" an existing console, register on sandbox.pubbly.com. It is hosted by us, and although you can upload, all content is wiped on a weekly basis.

#### Static Exports

To simply export what you have and see it running in a browser, 

* Chose File -> Export -> Project to Console
* Find the newly created zip file on your desktop (will be named same as project)
* Launch a pubbly console.
* Log into the pubbly console of your choosing
* Select "Static Exports"
* Create a new static export, and upload your exported zip.
    - Full instructions for creating and managing static exports on a pubbly console server at [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section Static Exports

### Exporting for Variable Export upload

To upload a "variable" export, which will be used to create a series of templated books,

* Create a pubbly book
* Choose File -> Asset Manager
* Move any assets you want to _change between templated children in series_ from the "Fixed" to the "Variable" column
* Close that window
* Chose File -> Export -> Project to Console
* Launch a pubbly console, or log into an existing one.
* Create a new Variable Export, and upload your exported zip.
* Create children based off that variable export
* Swap assets to create a series of templated content.
    - Full instructions for Creating and Managing Variable exports on a pubbly console server at [Pubbly Console](), section Variable Exports

### Exporting for Map upload

To create a pubbly map, which will link together multiple exports in a single downloadable zip,

* Create a pubbly book
    - Launch pubbly, file -> new, name your project
* Add a link
    - Click the Blue header text (Objects, Animations, Links) until you are on "Links"
    - Choose a shape tool (Polygon, square, circle) from the top right
    - Draw a link on 
* Name your link
    - Right click Link column (first column) and select "rename"
    - Enter a new name
* Add a To be Determined target
    - Right click target column of your link -> Other Targets -> To be Determined
* Export your project
* Upload your project to a pubbly console
    - You can upload this project as a Static or Variable, and you may also create a Stitched export from it.

Once the project is on the pubbly console, create a new map

* Go to Maps
* Click "New"
* Enter a new name for your map
* Select your map
* Click Edit

Add content to your map from either of the three export types (Stitched, Variable, Static) from the left hand column

* Select the type of export you want
* Select the export from the hirearchy (Stitched: School/Subject/Level), (Variable: Folder/Series), (Static: Folder)
* Double click to add to your map
* Page will refresh and a new "node" will be visible on the main area of your map.
* Move the export around the grey area to change it's location.

Upload a cover image to this node, so you know what it is.

* Select the node from the grey map area (will have a red border once selected)
* Bottom left node will update with selected node name
* Click the cover (currently empty) and select a png on your desktop
* Page will refresh with new "cover image" in place.

Upload, add, and position multiple nodes to your map. Once your map is loaded with content, determine which links go to which nodes

* Click a node on the map.
* All links with To Be Determined targets will load into the middle dropdown
* Select the target you wish to "determine"
* Shift select another node on the map
* Click the green ">" button to link that target inside that link inside that page of the left export to navigate to the shift clicked right export.
* Click the green ">>" button to link ALL targets inside your left export to navigate to the right export.

Determine an "entry point" for your map

* Select any node on the map
* Click the "star" button on the far right of the UI
* Viewing the map will now start you at the selected node

- You can preview a map from any node by selecting a node, and clicking the "eye glasses" button
- You can "save" the positioning of your map with the "save" button
- You can zoom in and out with the magnifier buttons

Update content referenced on map

* If you decide to change any referenced exports on a map, reupload new content whereever the "source" of the export is loaded.
    * If the export is a stitched unit, and you update _its_ source, first update the stitched.
* Once all exports have been "fixed", edit your map, and click the "Recycle" button (two circular arrows)

The process of updating a map takes time. We originally wanted to only update changed content, but time constraints forced us to implement a brute force method of simply re-copying and applying node connections to every node of the map.

Once your map is "perfect", select it in the map selection screen, and click the "Export for Local/APK" button. This will create and download a single zip file. This zip file works "out of the box". You can extract to a server. You can view offline from your local machine. You can also put the map inside a cordova project and export as an APK. Any link to the root folder's index.html file will "start" the map at the entry point specified, and all determined navigation nodes will refresh the browsers URL to the connected node.