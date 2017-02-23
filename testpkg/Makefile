PKGS="/root/lts-test"

all:
	cd $(PKGS) && apt-ftparchive packages . | gzip -c > Packages.gz
	cd $(PKGS) && apt-ftparchive -oAPT::FTPArchive::Release::Origin=lts-test release .  > Release
	echo "deb file:$(PKGS) ./" > /etc/apt/sources.list.d/lts-test.list
	echo "Package: *\nPin: release o=lts-test\nPin-Priority: 999\n" > /etc/apt/preferences.d/lts-test
	apt-get update

clean:
	rm -f /etc/apt/sources.list.d/lts-test.list /etc/apt/preferences.d/lts-test


