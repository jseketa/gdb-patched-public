# gdb-patched-public

Fixes for GDB and gdbserver (remote targets, non-stop, step-overs, pipe targets),
as one patch series on binutils-gdb master `BASE`.

    git clone https://sourceware.org/git/binutils-gdb.git && cd binutils-gdb
    git checkout -b patched $(cat ../gdb-patched-public/BASE)
    git am ../gdb-patched-public/patches/*.patch

Three changes in the series fix whole classes of crashes at their cause, in
place of earlier fixes of single sites: a remote target is no longer unpushed
while code still uses its threads when the connection fails, GDB never
resumes a program while connecting to it, and an event whose process has
gone is moot (PR gdb/18749).

Some of these are under review on gdb-patches; the rest are not sent yet.
Code and testsuite changes are included. License: GPL-3.0-or-later, as GDB.
