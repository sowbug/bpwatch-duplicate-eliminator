# bpwatch-duplicate-eliminator

The Android App [Blood Pressure (BP) Watch](https://play.google.com/store/apps/details?id=com.boxeelab.healthlete.bpwatch&hl=en) doesn't do duplicate detection/elimination when you import/export. I switch phones a lot, and I'll frequently import old backups expecting to treat the import operations as idempotent. So I ended up with 41 entries that exploded into 6,250 entries.

This utility eliminates the duplicates using the key (date, sys, dias, pulse). If you had multiple real readings on the same date that match that key, sorry. They'll be treated as duplicates.

Usage: `$ < BPWATCH_123.csv ./eliminate.py > BPWATCH_123-nodups.csv`

That will work for Linux/OS X. Figure out the equivalent for your platform.
