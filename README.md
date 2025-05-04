
# movie-cli

movie-cli is a Bash script for downloading TV series and movies from soaper.tv. It allows users to search for TV series or movies, select specific episodes, and download video and subtitle files.

## Installation

1. Install using apt:

  ```bash
  apt install movie-cli
  ```

2. Clone the repository:

   ```bash
   git clone https://github.com/hasanfq6/movie-cli.git
   ```

2. Make the script executable:

   ```bash
   chmod +x movie-cli.sh
   ```

3. Run the script:

   ```bash
   ./movie-cli

   or 

   movie-cli
   ```

## Usage

```bash
Usage:
  movie-cli [-n <name>] [-p <path>] [-e <num1,num3-num4...>] [-l] [-s] [-d] [-h | --help]

Options:
  -n <name>               TV series or Movie name
  -p <path>               media path, e.g: /tv_XXXXXXXX.html (ignored when "-n" is enabled)
  -e <num1,num3-num4...>  optional, episode number(s) to download
                          e.g: episode number "3.2" means Season 3 Episode 2
                          multiple episode numbers separated by ","
                          episode range using "-"
  -l                      optional, list video or subtitle link without downloading
  -s                      optional, download subtitle only
  -d                      enable debug mode
  -h | --help             display this help message

All usages:
  Search TV series or movies name and select the right one in fzf:
  movie-cli -n 'game of'

  If the media URI path is known:
  movie-cli -p /tv_34OGB6G6Zl.html

  Download Lucifer S01E01:
  movie-cli -n 'Lucifer' -e 1.1

  Support batch downloads: download Lucifer S01E01 to S01E05:
  movie-cli -n 'Lucifer' -e 1.1,1.2,1.3,1.4,1.5

  OR using episode range:
  movie-cli -n 'Lucifer' -e 1.1-1.5

  Display only video link:
  mpv "$($(dirname $0)/movie-cli.sh -n 'Game of throne' -e 1.1 -l)"

  Download subtitle only:
  movie-cli -n 'interstellar' -s

  Customize subtitle language:
  SOAPER_SUBTITLE_LANG=-en

  Download Movie:
  movie-cli -n 'interstellar'
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

