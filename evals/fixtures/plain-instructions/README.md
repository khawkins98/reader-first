# Lantern setup

Create a workspace. A workspace is the local folder where Lantern keeps the
files you are editing. The archive is a separate backup of those files.

Run `lantern restore --from archive.zip` if you already have an archive. This
replaces the files in your workspace. Select “Open workspace” to inspect them.

Enable incremental sync. Incremental sync sends only changed files to the
server after the first upload. You can leave it disabled for offline work.
