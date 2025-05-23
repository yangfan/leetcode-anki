
![build](https://github.com/prius/leetcode-anki/actions/workflows/build-deck.yml/badge.svg)
![style](https://github.com/prius/leetcode-anki/actions/workflows/style-check.yml/badge.svg)
![tests](https://github.com/prius/leetcode-anki/actions/workflows/tests.yml/badge.svg)
![types](https://github.com/prius/leetcode-anki/actions/workflows/type-check.yml/badge.svg)
![license](https://img.shields.io/github/license/prius/leetcode-anki)

# Leetcode Anki card generator

## Summary
By running this script you'll be able to generate Anki cards with all the leetcode problems.

I personally use it to track my grinding progress.

![ezgif-7-03b29041a91e](https://user-images.githubusercontent.com/1616237/134259809-57af6afb-8885-4899-adf8-a2639977baeb.gif)

![photo_2021-09-29_08-58-19 jpg 2](https://user-images.githubusercontent.com/1616237/135676120-6a83229d-9715-45fb-8f85-1b1b27d96f9b.png)
![photo_2021-09-29_08-58-21 jpg 2](https://user-images.githubusercontent.com/1616237/135676123-106871e0-bc8e-4d23-acef-c27ebe034ecf.png)
![photo_2021-09-29_08-58-23 jpg 2](https://user-images.githubusercontent.com/1616237/135676125-90067ea3-e111-49da-ae13-7bce81040c37.png)

## Prerequisites
1. [python3.8+](https://www.python.org/downloads/) installed
2. [python virtualenv](https://pypi.org/project/virtualenv/) installed
3. [git cli](https://github.com/git-guides/install-git) installed
4. [GNU make](https://www.gnu.org/software/make/) installed (optional, can run the script directly)
5. \*nix operating system (Linux, MacOS, FreeBSD, ...). Should also work for Windows, but commands will be different. I'm not a Windows expert, so can't figure out how to make it work there, but contributions are welcome.

## How to run
First download the source code
```sh
git clone https://github.com/prius/leetcode-anki.git
cd leetcode-anki
```

After that initialize and activate python virtualenv somewhere

Linux/MacOS
```sh
virtualenv -p python leetcode-anki
. leetcode-anki/bin/activate
```

Windows
```sh
python -m venv leetcode-anki
.\leetcode-anki\Scripts\activate.bat
```

Then initialize necessary environment variables. You can get it directly from your browser cookies (`csrftoken` and `LEETCODE_SESSION`)

Linux/Macos
```sh
export LEETCODE_CSRF_TOKEN="xxx"
export LEETCODE_SESSION_ID="yyy"
```

Windows
```sh
set LEETCODE_CSRF_TOKEN="xxx"
set LEETCODE_SESSION_ID="yyy"
```

And finally run for Linux/MacOS
```sh
make generate
```
Or for Windows
```sh
pip install -r requirements.txt
python generate.py
```

You'll get `leetcode.apkg` file, which you can import directly to your anki app.

Option `--ac True` means only ac problems are included; `False` means ac problems are excluded in the database. All problems are included if the option is not used.  
```sh
python3 generate.py --output-file all.apkg --ac True
```