# Utility Scripts

This directory contains a collection of scripts for performing various utility tasks.

---

## Backup Manager

This script is for backing up and synchronizing files and folders. It supports compression, incremental backups, exclusion patterns, and cleanup of old backups.

### Features

- **Compression**: Supports ZIP and TAR.GZ compression.
- **Incremental Backups**: Only backs up files that have changed.
- **Exclusion Patterns**: Exclude files and folders from the backup.
- **Cleanup**: Deletes old backups.

### Usage

To use the backup manager, run the script with the desired options.

#### Create a full backup

```bash
python3 backup_manager.py -s <source_dir> -d <dest_dir> -c zip

---

## Database Manager

This script is for managing MySQL and PostgreSQL databases, including backup and restore functionalities. It supports compression for backups and handles database credentials securely.

### Features

- **MySQL and PostgreSQL Support**: Manages both MySQL and PostgreSQL databases.
- **Backup and Restore**: Performs database backups and restores.
- **Compression**: Compresses backups to save space.

### Usage

To use the database manager, run the script with the desired options.

#### Backup a MySQL database

```bash
python3 db_manager.py mysql backup -d <database> -u <user> -p <password> -o <output_file>

---

## Dependency Installer

This script installs system and Python dependencies required by the script collection. It detects the Linux distribution and installs tools like `poppler-utils`, `ffmpeg`, `libpcap-dev`, `mysql-client`, and `postgresql-client`, along with Python packages from `requirements.txt`.

### Features

- **Distribution Detection**: Automatically detects the Linux distribution.
- **System and Python Dependencies**: Installs all necessary system and Python dependencies.

### Usage

To use the dependency installer, run the script with root privileges.

```bash
sudo bash dep.sh

---

## File Organizer

This script organizes files based on type, date, extension, or the first letter of their name. It supports recursive organization, dry-run mode, and duplicate file detection using MD5 hashes.

### Features

- **Multiple Organization Methods**: Organize files by type, date, extension, or first letter.
- **Recursive Organization**: Organize files in subdirectories.
- **Dry-Run Mode**: Preview the changes before they are made.
- **Duplicate File Detection**: Detects and handles duplicate files.

### Usage

To use the file organizer, run the script with the desired options.

#### Organize files by type

```bash
python3 file_organizer.py <directory> -by type

---

## PDF Tools

This script is a suite of tools for manipulating PDF files. It can merge, split, compress, and convert PDF files.

### Features

- **Merge**: Merge multiple PDF files into one.
- **Split**: Split a PDF file into multiple files.
- **Compress**: Compress a PDF file to reduce its size.
- **Convert**: Convert images to a PDF file.

### Usage

To use the PDF tools, run the script with the desired command and options.

#### Merge PDF files

```bash
python3 pdf_tools.py merge -i <file1.pdf> <file2.pdf> -o <merged.pdf>

---

## Web Scraper

This script is an advanced web scraper for extracting data from websites. It supports custom selectors, crawling, and data export.

### Features

- **Custom Selectors**: Use CSS selectors to extract specific data.
- **Crawling**: Crawl a website to a specified depth.
- **Data Export**: Export scraped data to JSON or CSV.

### Usage

To use the web scraper, run the script with the target URL and desired options.

#### Scrape a single page

```bash
python3 scraper.py <url>

---

## System Monitor

This script is a real-time system monitor that tracks CPU, memory, disk, and network usage.

### Features

- **Real-time Monitoring**: Tracks system resources in real time.
- **Resource Usage**: Monitors CPU, memory, disk, and network usage.
- **Alerts**: Sends alerts when resource usage exceeds a certain threshold.

### Usage

To use the system monitor, run the script with the desired options.

#### Monitor the system in real time

```bash
python3 sys_monitor.py

---

## Weather CLI

This script retrieves and displays current weather information for any city using the wttr.in service. It provides essential weather data like temperature, humidity, conditions, and wind speed in a clean, terminal-friendly format.

### Features

- **Simple and Detailed Formats**: Choose between compact one-line output or full ASCII art weather reports.
- **No API Key Required**: Uses the free wttr.in service that doesn't require authentication.
- **Comprehensive Error Handling**: Clear error messages for invalid cities, network issues, and timeouts.
- **Fast and Lightweight**: Quick responses with minimal dependencies.

### Installation

The Weather CLI requires the `requests` library. Install it using pip:

```bash
pip install requests
```

Or install all dependencies for the utility scripts:

```bash
pip install -r requirements.txt
```

### Usage

To use the Weather CLI, run the script with a city name and optional format parameter.

#### Get weather in simple format (default)

```bash
python3 weather_cli.py Paris
```

Output example:
```
Paris: ☀️  +22°C
```

#### Get weather in simple format (explicit)

```bash
python3 weather_cli.py "New York" --format simple
```

#### Get weather in detailed format

```bash
python3 weather_cli.py London --format detailed
```

Output example:
```
Weather report: London

     \  /       Partly cloudy
   _ /"".-.     18 °C          
     \_(   ).   ↓ 12 km/h      
     /(___(__)  10 km          
               0.2 mm
```

#### Get help

```bash
python3 weather_cli.py --help
```

### About wttr.in

The Weather CLI uses [wttr.in](https://wttr.in), a free and open-source weather service that provides:

- **No API Key Required**: No registration or authentication needed
- **Pre-formatted Output**: Weather data comes already formatted with emojis and ASCII art
- **Multiple Languages**: Supports various languages and locales
- **Reliable Data**: Uses data from multiple weather services for accuracy
- **No Rate Limits**: Reasonable usage is free and unlimited

This makes the Weather CLI extremely simple to set up and use compared to other weather APIs that require API keys and complex authentication.

### Troubleshooting

#### City Not Found Error

```
❌ Error: City 'Pariis' not found. Please check the spelling.
```

**Solution**: Double-check the city name spelling. Use common English names for cities (e.g., "Moscow" instead of "Moskva").

#### Connection Error

```
❌ Error: Unable to connect to weather service. Check your internet connection.
```

**Solution**: 
- Verify your internet connection is working
- Check if you can access https://wttr.in in your browser
- If behind a proxy, ensure your proxy settings are configured correctly

#### Timeout Error

```
❌ Error: Request timed out. Please try again.
```

**Solution**:
- The wttr.in service might be experiencing high load
- Wait a few seconds and try again
- Check your internet connection speed

#### Module Not Found Error

```
ModuleNotFoundError: No module named 'requests'
```

**Solution**: Install the requests library:
```bash
pip install requests
```

#### Special Characters Not Displaying

If emojis or special characters don't display correctly:

**Solution**:
- Ensure your terminal supports UTF-8 encoding
- Try a different terminal emulator (e.g., iTerm2 on macOS, Windows Terminal on Windows)
- Update your terminal fonts to include emoji support

### Examples

#### Check weather for multiple cities

```bash
python3 weather_cli.py Tokyo
python3 weather_cli.py "San Francisco"
python3 weather_cli.py Berlin --format detailed
```

#### Use in scripts

```bash
#!/bin/bash
# Check weather for your location
python3 weather_cli.py "Your City" --format simple
```

---

## YouTube Downloader

This script is a tool for downloading videos and audio from YouTube. It supports various formats and playlists.

### Features

- **Video and Audio Downloads**: Download both videos and audio from YouTube.
- **Format Selection**: Choose from a variety of video and audio formats.
- **Playlist Support**: Download entire playlists.

### Usage

To use the YouTube downloader, run the script with the video URL and desired options.

#### Download a video in the best quality

```bash
python3 youtube_downloader.py <url>
```

#### Download the audio of a video in MP3 format

```bash
python3 youtube_downloader.py <url> -a
```

#### Monitor the system and log the data to a file

```bash
python3 sys_monitor.py -l system_log.json
```

#### Crawl a website and save the data to a JSON file

```bash
python3 scraper.py <url> -d 2 -o scraped_data.json
```

#### Split a PDF file

```bash
python3 pdf_tools.py split -i <input.pdf> -o <output_directory>
```

#### Organize files by date with recursive organization

```bash
python3 file_organizer.py <directory> -by date -r
```

#### Restore a PostgreSQL database

```bash
python3 db_manager.py postgres restore -d <database> -u <user> -p <password> -i <input_file>
```

#### Create an incremental backup

```bash
python3 backup_manager.py -s <source_dir> -d <dest_dir> -i
```