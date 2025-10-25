# Gunakan base Arch Linux
FROM archlinux:latest

# Update dan install tools dasar
RUN pacman -Syu --noconfirm && \
    pacman -S --noconfirm openssh sudo git base-devel vim

# Aktifkan SSH server
RUN ssh-keygen -A && \
    echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config && \
    echo 'PasswordAuthentication yes' >> /etc/ssh/sshd_config && \
    echo 'root:root' | chpasswd

# Buka port SSH
EXPOSE 22

# Jalankan SSH server ketika container start
CMD ["/usr/sbin/sshd", "-D"]
