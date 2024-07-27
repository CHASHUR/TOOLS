YouTube-DL (yt-dlp) is a command-line program to download videos from YouTube and a few more sites. Here are some key points and common usage examples for yt-dlp:

Installation

To install yt-dlp, you can use pip (Python package installer):

bash
pip install yt-dlp


Alternatively, you can download the standalone binary:

1. Windows**: Download the binary from [yt-dlp releases](https://github.com/yt-dlp/yt-dlp/releases) and place it in a folder included in your system's PATH.
2. Linux/MacOS**: You can use wget or curl to download the binary:
   bash
   sudo wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -O /usr/local/bin/yt-dlp
   sudo chmod a+rx /usr/local/bin/yt-dlp
   

 Basic Usage

To download a video from YouTube, you can use the following command:

bash
yt-dlp <URL>


Replace `<URL>` with the actual URL of the YouTube video.

### Downloading Playlists

To download a playlist, simply provide the playlist URL:

```bash
yt-dlp <playlist_URL>
```

### Selecting Resolution

To specify the resolution, you can use the `-f` flag. For example, to download a video in 720p:

```bash
yt-dlp -f 'bestvideo[height<=720]+bestaudio/best[height<=720]' <URL>
```

### Downloading Audio Only

To download only the audio, you can use the `-x` flag, which stands for "extract audio":

```bash
yt-dlp -x <URL>
```

You can also specify the audio format using the `--audio-format` flag:

```bash
yt-dlp -x --audio-format mp3 <URL>
```

### Custom Output Template

To customize the output file name, you can use the `-o` flag followed by the desired template:

```bash
yt-dlp -o '%(title)s.%(ext)s' <URL>
```

### Updating yt-dlp

To keep yt-dlp up to date, you can run:

```bash
yt-dlp -U
```

### Common Options

- `-k` or `--keep-video`: Keep the video file after extracting audio.
- `-ciw`: Continue on errors, ignore errors for unavailable videos, write info files.
- `--download-archive`: Record downloaded videos in a file and skip them on future downloads.

### Example: Download a Playlist with Specific Resolutions

```bash
yt-dlp -f 'bestvideo[height<=1080]+bestaudio/best[height<=1080]' <playlist_URL>
```

### Example: Download and Convert Audio to MP3

```bash
yt-dlp -x --audio-format mp3 <URL>
```

### Example: Custom Output Template with Playlist

```bash
yt-dlp -o '%(playlist_index)s - %(title)s.%(ext)s' <playlist_URL>
```

For further details, you can always refer to the [yt-dlp documentation](https://github.com/yt-dlp/yt-dlp#usage-and-options) and explore more advanced options and configurations.