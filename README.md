# assets-uploader
Command line tool to robustly upload Github release assets.  

## Features
- Upload file to Github Release Assets that identified by `tag`.    
- Allow `overwrite` if file exists.
- With the optional `-releasename` flag an upload to the newest existing release by name (e.g. a draft one)

## Build 
```bash
$ cd cmd/github-assets-uploader
$ go build
```

## Usage
- help
```bash
$ github-assets-uploader -h
Usage of ./github-assets-uploader:
  -f string
        File path to upload.
  -mediatype string
        E.g., 'application/zip'. (default "application/gzip")
  -overwrite
        Overwrite release asset if it's already exist.
  -repo string
        Github repo, e.g., 'ui86/assets-uploader'.
  -tag string
        Git tag to identify a Github Release in repo.
  -releasename string
        Upload an asset to the newest existing release by name.
  -token string
        Github token to make changes.
  -version
        Print version and exit. 
```

- example    
```bash
$ github-assets-uploader -f vt2geojson-v0.1.5.1-testonly-linux-386.tar.gz -mediatype application/gzip -overwrite -repo ui86/vt2geojson -token *** -tag v0.1.5.1-testonly
```
