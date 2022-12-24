FROM docker.io/library/golang:latest


RUN mkdir test

# failed to initialize build cache at /go/test: mkdir /go/test/00: permission denied
# が発生した為、追記
RUN chgrp -R 0 test && \
    chmod -R g=u test

COPY main.go test

USER 1001

EXPOSE 8080

#CMD ["sh", "-c", "GOCACHE=off", "go", "run", "/go/test/main.go"]
CMD export GOCACHE=/go/test;go run /go/test/main.go
