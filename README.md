# SoccerNet package

```bash
pip install -e https://github.com/ho0-kim/SoccerNet-S3
pip install -e .
```

## Usage
---
### Prerequisite
To access S3 bucket, you need to follow this instruction, [AWS Configuration](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html#configuration).

### Stream data into S3 Bucket
```python
from SoccerNet.Downloader import SoccerNetDownloader

mySoccerNetDownloader = SoccerNetDownloader(LocalDirectory="path/to/savedir") # "LocalDirectory" refers to the directory where data is stored, encompassing both directories within both the local environment and an S3 bucket.

mySoccerNetDownloader.password = "Password for videos (received after filling the NDA)"
mySoccerNetDownloader.s3_bucket = "AWS S3 Bucket Name" # if it is None, it will download data into local

mySoccerNetDownloader.downloadGames(files=["1_720p.mkv", "2_720p.mkv"], split=["train","valid","test","challenge"])
mySoccerNetDownloader.downloadGames(files=["1_224p.mkv", "2_224p.mkv"], split=["train","valid","test","challenge"])
```
