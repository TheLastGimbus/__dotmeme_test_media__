# dotmeme test media
## What is this?
This is a repo containing test media (memes) for [dotmeme](https://github.com/TheLastGimbus/dotmeme) app

It is used by `MockMediaManager`, which emulates folder from smartphone on headless testing env

## Structure
There is main `index.json` file which holds all important information

`paths` folder contains all folders, which contain files (memes)

Folder structure should be like this:
```
_test_media/  // Root folder
├── README.md
├── index.json  // index containing info about *all* files
└── paths/
    ├── Camera/  // One folder (AssetPathEntity)
    │   └── IMG_20210709_164812.jpg  // One file (AssetEntity)
    ├── Reddit/
    │   ├── meme.jpg
    │   └── another_meme.jpg
    └── Screenshots/
```

Structure for `index.json` file *has* to be like this:
```json
{
  "paths": {
    "876683": {  // Path id - must be a random and unique integer
      "path": "paths/Reddit/",  // Folder path - relative to index file
      "assets": {  // All assets inside it
        "437854092489234": {  // Also random and unique int
          "filename": "goth_girl_rule.jpg",  // Relative to folder
          "lastModified": 1625853387,  // Unix epoch
          "duration": 0  // Duration for video - 0 for photos
        },
        "1315402535634264": {
          "filename": "iphone_rule.jpg",
          "lastModified": 1625843300,
          "duration": 0
        }
      }
    }
  }
}
```

