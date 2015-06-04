#viddick - chronicles of a capture program

viddick is a tool to quickly take and share screenshots, videos
and other files. It uses escrotum for the capturing and simply
moves the file to a specified location on a webserver and echos
the generated url.

#Optional Requirements
* escrotum for taking pictures and videos
* zenity for selecting files with a file dialog
* xclip for copying the result into the clipboard
* notify-send for showing notifications

#Configuration
The script expects a locally mounted folder where it can move the files into,
a folder in that mount where the files should be stored in and finally the url
that points to the mounted folder. Optionally the filename can be set via a
variable otherwise it will use the basename of the generated file.

e.g
```bash
destinationPrefix="/mount/server"
destinationFolder="uploads"
destinationFile=$(basename "$file")
hostPrefix="https://host.foo"


#results
$localFolder="/mount/server/uploads"
$destination="/mount/server/uploads/filename"
$url="https://host.foo/uploads/filename"
```

Or simply rewrite the uploadFile function to a custom upload method

#Copyright:
Code is under the MIT License and written by Zod-<br>
Idea for the name by Muxgux

#Usage
```
USAGE:
  viddick [OPTION] [FILE]

OPTIONS:
  -a, --all     capture the entire desktop (default)
  -s, --select  select an area or application to capture
  -r, --record  record a video instead of taking a screenshot
                call this again to stop recording
  -d, --dialog  upload a specific file choosen with zenity file dialog
  -m, --move    delete the local file after copying
  -x, --xclip   copy the result into the clipboard after uploading
  -n, --notify  show a notification with the result url

  -h, --help    displays this

FILE:
  FILE          direct path of a file to upload
```
