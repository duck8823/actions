FROM golang:1.11-alpine

LABEL "repository"="https://github.com/duck8823/actions"
LABEL "homepage"="https://github.com/duck8823/actions"
LABEL "maintainer"="<shunsuke maeda> duck8823@gmail.com"

LABEL "com.github.actions.name"="Go Report Card"
LABEL "com.github.actions.description"="Run Go Report Card"

RUN apk --update add --no-cache git curl

RUN curl -L https://git.io/vp6lP | sh
RUN go get github.com/gojp/goreportcard/cmd/goreportcard-cli

WORKDIR /workdir

ENTRYPOINT ["goreportcard-cli"]