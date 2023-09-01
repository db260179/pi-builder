FROM archlinux/archlinux:base

RUN mkdir -p /etc/pacman.d/hooks \
	&& ln -s /dev/null /etc/pacman.d/hooks/30-systemd-tmpfiles.hook

RUN pacman -Syu --noconfirm --needed \
		arp-scan \
		python \
		parted \
		dosfstools \
		rsync \
	&& rm -rf /var/cache/pacman/pkg/*

RUN mkdir /tools
COPY install-binfmt /tools/
COPY docker-extract /tools/
COPY disk /tools/
COPY card-install /tools/
