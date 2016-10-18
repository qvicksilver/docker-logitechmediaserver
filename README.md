# Docker Container for Logitech Media Server

This is a Docker image for running the Logitech Media Server package.
Runs the latest 7.9 nightly build.

Run completely containerized:

    docker run -d \
               -p 9000:9000 \
               -p 3483:3483 \
               -p 3483:3483/udp \
               -v <audio-dir>:<somewhere-in-container> \
               qvicksilver/logitechmediaserver

With persistent data on host:

    docker run -d \
               -p 9000:9000 \
               -p 3483:3483 \
               -p 3483:3483/udp \
               -v <audio-dir>:<somewhere-in-container> \
               -v <data-dir>:/var/lib/squeezeboxserver \
               -v <log-dir>:/var/log/squeezeboxserver \
               qvicksilver/logitechmediaserver <uid>

Where <uid> matches the uid of a user on the host with write permissions
on the <data-dir> and <log-dir> directories.
