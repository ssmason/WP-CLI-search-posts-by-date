=== CLI  ===
Contributors:      Stephen Mason
Tags:              block
Tested up to:      v0.0.1
Stable tag:        v0.0.1
License:           GPL-2.0-or-later
License URI:       https://www.gnu.org/licenses/gpl-2.0.html



A WP-CLI Command
- This command will take optional date-range arguments like --start-date and --end-date 
- If the dates are omitted, the command will default to the last 30 days.
- The command will execute a WP_Query search for Posts within the date range looking for posts containing the a forementioned Gutenberg block names in the options --block-name
- The command will log to STDOUT all Post IDs for the matching results.
- If no posts are found, or any other errors encountered, output a log message.

== Installation ==

create a directory in your theme 
```
/wp-cli
```
drop dmg-query.php in this directory

in functions.php or where you position the file in your file structure
```
include_once __DIR__ . '/wp-cli/dmg-query.php';
```

when this is done, on refresh you will be able to see select as a subcommand on the command

```
wp
```

== Frequently Asked Questions ==

= How do i use the CLI Command =

subcommand vars: 
```
Subcommand vars:

--block-name=<string>     Filter by block name (e.g. core/paragraph, core/image, etc.)
--start-date=<date>       Start date in YYYY-MM-DD format (optional)
--end-date=<date>         End date in YYYY-MM-DD format (optional)
--dry-run                 Run the command without making any changes
```

commands : 
```
wp dmg-read-more select --block-name=create-block/dmg-post-selector #no date range so last 30 days
wp dmg-read-more select --block-name=create-block/dmg-post-selector --start-date=1970-01-01 --end-date=2026-01-01 #date range and block name
wp dmg-read-more select --start-date=1970-01-01 --end-date=2026-01-01 #date range only
```
Any block can be searched for just by updating the --block-name variable
```
wp dmg-read-more select --block-name=core/paragraph #a different block name
```


== Changelog ==

= 0.0.1 =
* Release

