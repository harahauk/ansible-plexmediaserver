## PlexTraktSync Docker-container ##
#  @author Harald Hauknes <harald (at) hauknes.org>
#
# Initial setup with `docker run plextraktsync plextraktsync`
# Optional testing with `docker run plextraktsync sync`
#
# Path to configuration-files:
# '/root/.config/PlexTraktSync'
#
# Example:
# 'docker run -d --restart unless-stopped --name plextraktsync -v
# /home/shad0t/docker-data/PlexTraktSync/root-config-PlexTraktSync/:/root/.config/PlexTraktSync hauknesdotorg/plextraktsync:latest'
FROM dhi.io/python:3.13-debian13-dev
# The above is a hardened image, do not "apt update"
# Requires "docker login dhi.io" to pull
# NOTE: 'bash' is not really a requirement, used for debugging
# RUN apt install -y bash # git
# Optially build the package via git
# RUN git clone https://github.com/Taxel/PlexTraktSync
RUN pip install plextraktsync
CMD [ "plextraktsync", "watch" ]
