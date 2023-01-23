Build Instructions
------------------
Create a build directory

	mkdir lineage
	cd lineage

Initialize your local repository using the LineageOS trees, use a command like this:

    repo init -u https://github.com/LineageOS/android.git -b lineage-19.1

Now create a local_manifests directory

    mkdir .repo/local_manifests

Copy my local manifest 'debx.xml' to the 'local_manifests' directory.

    curl -L -o .repo/local_manifests/debx.xml -O -L https://raw.githubusercontent.com/notakbuzz/android_local_manifest_deb/lineage-19.1/debx.xml

Then to sync up:

    repo sync -c --force-sync

OR, for those with limited bandwidth/storage:

    repo sync -c --no-clone-bundle --no-tags --force-sync --optimized-fetch --prune


Now start the build...

```bash
# Go to the root of the source tree...
$
# ...and run to prepare our devices list
$ . build/envsetup.sh
# ... now run
$ brunch deb
```


Please see the [LineageOS Wiki](https://wiki.lineageos.org/) for further information.
