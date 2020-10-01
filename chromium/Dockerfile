FROM alpine:edge

RUN apk update --no-cache && apk add --no-cache chromium x11vnc xvfb dbus
RUN mkdir ~/.vnc
RUN x11vnc -storepasswd 4321 ~/.vnc/passwd
RUN sh -c 'echo "exec chromium-browser --no-sandbox --disable-gpu" > /.xinitrc'

EXPOSE 5900

CMD    ["x11vnc", "-forever", "-usepw", "-permitfiletransfer", "-create"]
