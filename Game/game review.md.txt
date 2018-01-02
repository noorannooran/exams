# Game Dev Quiz Review
## Quiz 2 (Week 2)

### Unity Project:
- Raw game assets
- unity editor settings
- asset linkages

### Project Folder
- Assets
- ProjectSettings
- Library, Temp

### Assets:
- meshes, textures, audio, text
	- do not exist in Scene Hierarchy
	-GameObjects --> reference assets

### Types:
- Prefabs
- Data Files
- Textures
- Meshes
- Materials
- Audio and Video
- Animation Clips, Controllers, Cubemaps

### Prefab:
- reusable GameObject asset
	- can be instantiated
	- changes applied to prefab are applied to all instances
	- can break away from it's link

### Data Files
- Plain Text
	- hold game data
- Binary Files
	- DLLs (compiled source code)
	- textures store data
- Source Code Data Files
	- game scripts
	- variable & constants
	- data structures
- Other
	- CSV (comma separated values)
	- JSON
	- XML

### Inspector View	
- store and modify game data inside Unity
	- using Serialize Field



### Texture Assets:
- a sprite
- sprite atlas
- mesh skin (UV map)
- Formats: PNG, JPEG, PSD

#### Sprite:
- 2D game grapjic
- GUI element

#### Animated Sprites
- using a sprite atlas as an animation sequence

#### Mesh UV Map
- 2D image wrapped onto 3D mesh
- U = X V = Y coordinates
- "skin" of mesh
- mapping between *vertices* done in external 3D modelling applications
	- import mesh file into Unity

#### Mesh Asset
- representd 3D geometry
- defines 2D geometry
- can be flat plane with Sprite applied as texture
- Formats:
	- FBX
	- 3DS
	- MAX
	- MA
	- BLEND

#### Mesh Channels
- channels = *information*
- Geometry: defines geometric structure
	- vertices
	- edges
	- triangles
	- polygons
- UV Mapping
	- how textures are *wrapped* or *projected* onto surface of 3D model
- Animation and Rigging
	- store all key frames that define how it *changes* or *animates* over time

### Material
- asset that can be attached to a Mesh Component
- references **Shader script**
- Materials link **shaders** and **meshes** together

#### Material Shaders
- shader scripts can take **input** define Material properties:
	- texture
	- numerical values
	- color values

### Audio and Video
- Audio Formats
	- WAV
	- MP3
	- OGG
- Video Formats
	- AVI
	- MOV
	- MPG, MPEG
- quality varies with format

### Asset Importing
- Textures
- Meshes
- Audio, Visual
- Other

### Texture Importing
- textures used are **imported** versions of source files in Assets
- Unity generates optimized versions of imported textures
- import process does not affect original files
- assigned a **type** in inspector view
	- Standard
	- GUI
	- Sprite

#### Texture Import Guidelines
- highest quality format
- largest size possible : 
	- 4096x4096 desktop
	- 2048x2048 mobile
- larger == longer import times
- reasonable import sizes:
	- 512*512
	- 1024*1024
- large texture sizes: sprite atlases

#### Highest Quality Formats
1. Lossless format
	- PSD
2. High Quality Compression
	- PNG: transparencies
	- JPEG: opaque

#### Standard Textures
- use **power-of-two** pixel dimensions for all **Standard Textures**
	- e.g. mesh UV map
- pixel dimensions can be **rectangular**

#### Mesh Import Guidelines
1. Minimize polygon and vertex count
	- detail is determined by polygon count
	- more polygon == greater computing power req.
2. Minimize number of Materials
	- each introduces a draw cell/ rendered frame
3. Batch local meshes
	- combine several meshes into a single mesh
	- minimize number of GameObjects

#### Audio and Video Import Guidelines
- compressed, lossy format
- importing uncompressed WAV and AVI source files recommended

##### Types of Import Formats
1. Native (AIFF, WAV)
	- pros:
		- no decoding = faster engine processin
	- cons:
		- greater file size = increased game size
	- use for short sound clips
2. Compressed (OGG Vorbis)
	- pros:
		- smaller file size
	- cons:
		- decoded each time loaded = impacted engine performance
	- use for long clips (background sounds and music)

### Asset Management Tools

#### Project Panel
- hierarchical lists of all assets
- specialized view of assets folder
- don't make changes at the OS level

#### Hierarchy Panel
- lists all objects in scene
- scene objects defined by GameObjects
	- can link to Prefabs
	- audio clips, textures, meshes

#### Importing Assets into Project

#### Object Inspector
- each asset has type-specific properties
- **Asset Properties**:
	- how instances of asset appear/ behave
- Prefabs:
	- instances of prefab follow settings
- Textures:
	- all Material components follow texture's import settings
- Materials:
	- all meshes using Material will exhibit same style

#### Folders and Favourites
##### Folders
- keep your project organized so it doesn't become unmanageable
- folder names according to types of assets they represent
- naming conventions
- Folders: 
	- Contain related assets
	- follow consistent naming convention
	- structured into subfolders of related assets
- all assets inside *contents* folder, under root assets folder
- place all scripts in Assets/Contents/Scripts
- Assets/Contents/Prefabs
- Assets/Contents/Textures

##### Favourites
- Shortcuts
- Search Filters
- Search Range
	- entire asset folder
	- current selected folder
	- asset store

### Asset Store
- Project Panel
- can search
- Free Assets VS Paid Assets
- can use search filters

