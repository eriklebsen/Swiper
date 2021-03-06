# Swiper
A poor, roughly shod implementation of what would happen if Swiper the Fox took up programming staff directory databases.

## What it does
This simple Ruby script *swipes* (haha, get it?) images from the web, writes them to the filesystem, and updates the database column that provided the URL with the file name. It relies on an existing SQLite database.

There's another script in here (`differences.rb`) to compare two versions of the column, reporting those with newly added images.

*Dora will never find them now!*

## Implementation details
Requires `sqlite3`, which probably limits Swiper to Ruby 1.9 environments. The documentation for Ruby's various SQLite modules do not seem entirely clear to me on this and frankly, I didn't verify this beyond what it took to get Swiper running.

If Swiper encounters invalid URLs in the supplied database column, it reports the failure and tries the next URL. In the case of such errors, the database and any existing images in the directory remain unchanged.
