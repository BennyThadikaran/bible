> **Man shall not live on bread alone,
> but on every word that comes out of the mouth of God. - Mathew 4:4**

# Bible

This is a command line python script, i wrote back in 2019 to aid my daily reading of the Holy Bible.

The Holy Bible is not a single book. It a collection of books written at different time periods.

Reading the Bible cover to cover on your first attempt is sure to leave you confused.

> A 365 day chronological plan allows you to read the Bible in the order the events happened.

This script prints out the Bible reading for the day and has other helpful features. See [Usage](#usage) below.

Works on both Linux and Windows with Python3 installed.
Uses standard library, No dependencies.

The reading plan itself was picked up from [biblestudytools.com](https://www.biblestudytools.com/bible-reading-plan/chronological.html).

## Installation

**Supports Python version >= 3.7**

1. Clone or download the repo: `git clone https://github.com/BennyThadikaran/bible.git`
2. Open your terminal(Linux) or Powershell (Windows).
3. Navigate to the project folder
4. For Linux users, make the script executable with `chmod +x bible`
5. Execute script as `./bible`

## Usage

Start a new plan with `-s/--start` type 'y' when prompted.

```
$ ./bible -s
Start a new Bible plan.
Are you sure? (Y/N) y
Done.
         For I know the plans I have for you, declares the Lord,
         plans for welfare and not for evil,
         to give you a future and a hope.
                    - Jeremiah 29:11
```

Now `./bible` will print the reading for today.

```
$ ./bible
Sun, 19 Mar 2023: Genesis 1-3

```

To check next days reading, use the `-n/--next` option

```
$ ./bible -n
Sun 19 Mar 2023: Genesis 1-3 (Today)
Mon 20 Mar 2023: Genesis 4-7
```

You can also check next several days reading by providing a number like `-n 3`

```
$ ./bible --next 3
Sun 19 Mar 2023: Genesis 1-3 (Today)
Mon 20 Mar 2023: Genesis 4-7
Tue 21 Mar 2023: Genesis 8-11
Wed 22 Mar 2023: Job 1-5
```

Similarly you can check the previous day reading with `-p/--prev`

```
$ ./bible -p 2
Fri 17 Mar 2023: Job 17-20
Sat 18 Mar 2023: Job 21-23
Sun 19 Mar 2023: Job 24-28 (Today)
```

To get the reading for a specific date use the `-d/--date` option. Pass an ISO format date (YYYY-MM-DD)

```
$ ./bible -d 2013-3-14
Tue, 14 Mar 2023: Job 6-9

```

To see your reading progress, use `-stats`

```
$ ./bible -stats
9 days (2.47%) of plan completed.
```

Every once in a while, you might miss several days of reading.

Rather than catching up, you can just continue from the last reading date.

Use the `-c/--continue` passing an ISO format date (YYYY-MM-DD)
Type y after confirming the date and reading.

```
$ ./bible -c 2023-3-15
Continue reading from Wed Mar 15 2023: Job 10-13.
Confirm (Y/N) y
```

I like [bible-studys.org](https://bible-studys.org) for their explantations, commentary and historical context. So i added an option to print the website link for all readings.

Use `-l/--link` on its own or with the `--date` option

```
$ ./bible -l
Sun, 19 Mar 2023: Genesis 1-3

Study links
https://bible-studys.org/genesis-chapter-1
https://bible-studys.org/genesis-chapter-2
https://bible-studys.org/genesis-chapter-3

```

**Ofcourse, if you forget these commands, use the `--help` option to print all commands.**

Notice there are short options just like any linux terminal app.

```
$ ./bible -help
usage: bible [-h] [-l] [-stats] [-p [N] | -n [N] | -s | -c YYYY MM DD | -d YYYY MM DD]

Prints daily Bible reading using a Chronological 1 year plan

options:
  -h, --help            show this help message and exit
  -l, --links           Print study links
  -stats                Prints reading progress
  -p [N], --prev [N]    Print previous N days readings. N defaults to 1
  -n [N], --next [N]    Print next N days readings. N defaults to 1
  -s, --start           Create new plan
  -c YYYY MM DD, --continue YYYY MM DD
                        Continue reading from specified date
  -d YYYY MM DD, --date YYYY MM DD
                        Get reading for specified date

Be strong and courageous. Do not fear or be in dread of them, for it is the Lord your
God who goes with you. He will not leave you or forsake you. - Deuteronomy 31:6
```

**For convenience, I have included `bible-plan.pdf` that contains the entire 365 days plan**
