FROM        node:16.19.0-alpine3.17

            # Pass this to map volume rights to HOST_UID,
            # docker build --build-arg HOST_UID=$(id -u) --tag photo-game-react-native-ts .
            # UID 1000 for most single user stations
ARG         HOST_UID="1000"
ARG         HOST_USER="virt-user"
ARG         WORKDIR="/app"

WORKDIR     "${WORKDIR}"
VOLUME      "${WORKDIR}"

            # Not ideal HACK but works, move node user to be able to apply HOST_UID
RUN         sed -e "s|1000|10000|g" -i /etc/group
RUN         sed -e "s|1000|10000|g" -i /etc/passwd
RUN         adduser --disabled-password "${HOST_USER}" -u "${HOST_UID}"
RUN         addgroup "${HOST_USER}" node

USER        "${HOST_USER}"
ENTRYPOINT  ["sh"]
