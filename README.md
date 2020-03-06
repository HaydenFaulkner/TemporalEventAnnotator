<h1 align='center'>Temporal Event Annotator</h1>
<p align=center>
A <a href="https://www.qt.io/">QT</a> tool used to annotate temporal segments of a video with events which each have unique and customisable information.
</p>

![The Annotator](annotator.png)

### Process for Usage
Simply run `run.py` with arguments specifying the video file, a save path to save annotations `.json` (see format below), 
and a type file (described below)
```shell script
$ python run.py --video_file data/videos/V006.mp4 --save_path data/annotations --type_file data/annotations/classes.txt 
```

### Type file (`classes.txt`)
Specifies the default classes and their default custom entries
```text
Match	
Set	Winner,Score,Near
Game	Winner,Score,Server
Point	Winner,Score
Hit	Player,Side,Type
Serve	Player,Result

```

### Save files (`.json`)
The annotator generates .json files consisting of the following data structure format:
```json
{
    "video":"data/videos/V006.mp4",
    "classes":{
        "USE":[
            {
                "custom":{

                },
                "name":"0001",
                "start":25481,
                "desc":"",
                "end":120405
            }
        ],
        "SPLITS":[
            {
                "custom":{
                    "Type":"Train"
                },
                "name":"0001",
                "start":25529,
                "desc":"",
                "end":87022
            },
            {
                "custom":{
                    "Type":"Val"
                },
                "name":"0002",
                "start":87032,
                "desc":"",
                "end":94849
            },
            {
                "custom":{
                    "Type":"Test"
                },
                "name":"0003",
                "start":94856,
                "desc":"",
                "end":120320
            }
        ],
        "Set":[
            {
                "custom":{
                    "Near":"Williams",
                    "Winner":"Williams",
                    "Score":"1-0"
                },
                "name":"0001",
                "start":25595,
                "desc":"",
                "end":71191
            },
            {
                "custom":{
                    "Near":"Sharapova",
                    "Winner":"Williams",
                    "Score":"2-0"
                },
                "name":"0002",
                "start":74472,
                "desc":"",
                "end":120080
            }
        ],
        "Match":[
            {
                "custom":{

                },
                "name":"0001",
                "start":25525,
                "desc":"",
                "end":120354
            }
        ],
        ...
    }
}
```

