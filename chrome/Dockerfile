FROM archlinux/base
RUN pacman -Syu --noconfirm && \
	pacman -S --noconfirm \
			base-devel \
			git \
			sudo
RUN useradd -m user && \
	passwd -d user && \
	printf 'user ALL=(ALL) ALL\n' | tee -a /etc/sudoers
WORKDIR /home/user
USER user
RUN git clone https://aur.archlinux.org/google-chrome.git && \
	cd google-chrome && \
	makepkg -si --noconfirm && \
	sudo rm -r /var/cache/pacman/pkg && \
	sudo rm -r /var/lib/pacman
ENTRYPOINT ["google-chrome-stable"]
