# youtube-dl

## USAGE
youtube-dl [OPTIONS] URL

## DESCRIPTION
**youtube-dl** is a small command-line program to download videos from
YouTube.com and a few more sites. It requires the Python interpreter, version
2.x (x being at least 5), and it is not platform specific. It should work in
your Unix box, in Windows or in Mac OS X. It is released to the public domain,
which means you can modify it, redistribute it or use it however you like.

## OPTIONS
    -h, --help               print this help text and exit
    -v, --version            print program version and exit
    -U, --update             update this program to latest version
    -i, --ignore-errors      continue on download errors
    -r, --rate-limit LIMIT   download rate limit (e.g. 50k or 44.6m)
    -R, --retries RETRIES    number of retries (default is 10)
    --playlist-start NUMBER  playlist video to start at (default is 1)
    --playlist-end NUMBER    playlist video to end at (default is last)
    --dump-user-agent        display the current browser identification

### Filesystem Options:
    -t, --title              use title in file name
    -l, --literal            use literal title in file name
    -A, --auto-number        number downloaded files starting from 00000
    -o, --output TEMPLATE    output filename template
    -a, --batch-file FILE    file containing URLs to download ('-' for stdin)
    -w, --no-overwrites      do not overwrite files
    -c, --continue           resume partially downloaded files
    --cookies FILE           file to dump cookie jar to
    --no-part                do not use .part files
    --no-mtime               do not use the Last-modified header to set the file
                             modification time
    --write-description      write video description to a .description file
    --write-info-json        write video metadata to a .info.json file

### Verbosity / Simulation Options:
    -q, --quiet              activates quiet mode
    -s, --simulate           do not download video
    -g, --get-url            simulate, quiet but print URL
    -e, --get-title          simulate, quiet but print title
    --get-thumbnail          simulate, quiet but print thumbnail URL
    --get-description        simulate, quiet but print video description
    --get-filename           simulate, quiet but print output filename
    --no-progress            do not print progress bar
    --console-title          display progress in console titlebar

### Video Format Options:
    -f, --format FORMAT      video format code
    --all-formats            download all available video formats
    --max-quality FORMAT     highest quality format to download

### Authentication Options:
    -u, --username USERNAME  account username
    -p, --password PASSWORD  account password
    -n, --netrc              use .netrc authentication data

### Post-processing Options:
    --extract-audio          convert video files to audio-only files (requires
                             ffmpeg and ffprobe)
    --audio-format FORMAT    "best", "aac" or "mp3"; best by default

## FAQ

### Can you please put the -b option back?

Most people asking this question are not aware that youtube-dl now defaults to downloading the highest available quality as reported by YouTube, which will be 1080p or 720p in some cases, so you no longer need the -b option. For some specific videos, maybe YouTube does not report them to be available in a specific high quality format you''re interested in. In that case, simply request it with the -f option and youtube-dl will try to download it.

### I get HTTP error 402 when trying to download a video. What''s this?

Apparently YouTube requires you to pass a CAPTCHA test if you download too much. We''re [considering to provide a way to let you solve the CAPTCHA](https://github.com/phihag/youtube-dl/issues/8), but at the moment, your best course of action is pointing a webbrowser to the youtube URL, solving the CAPTCHA, and restart youtube-dl.

### I have downloaded a video but how can I play it?

Once the video is fully downloaded, use any video player, such as [vlc](http://www.videolan.org) or [mplayer](http://www.mplayerhq.hu/).

### The links provided by youtube-dl -g are not working anymore

The URLs youtube-dl outputs require the downloader to have the correct cookies. Use the `--cookies` option to write the required cookies into a file, and advise your downloader to read cookies from that file.

### ERROR: no fmt_url_map or conn information found in video info

youtube has switched to a new video info format in July 2011 which is not supported by old versions of youtube-dl. You can update youtube-dl with `sudo youtube-dl -U`.

## COPYRIGHT
**youtube-dl**: Copyright © 2006-2011 Ricardo Garcia Gonzalez. The program is
released into the public domain by the copyright holder. This README file was
originally written by Daniel Bolton (<https://github.com/dbbolton>) and is
likewise released into the public domain.

## BUGS
Bugs and suggestions should be reported at: <https://github.com/phihag/youtube-dl/issues>
