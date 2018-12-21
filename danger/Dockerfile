FROM ruby:2.5-alpine

LABEL "repository"="https://github.com/duck8823/actions"
LABEL "homepage"="https://github.com/duck8823/actions"
LABEL "maintainer"="<shunsuke maeda> duck8823@gmail.com"

LABEL "com.github.actions.name"="Danger"
LABEL "com.github.actions.description"="Run Danger"
LABEL "com.github.actions.icon"="alert-triangle"
LABEL "com.github.actions.color"="yellow"

RUN apk update \
 && apk add jq git \
 && rm -rf /var/cache/apk/*

RUN gem install specific_install \
 && gem specific_install https://github.com/duck8823/danger feature/ci_source/github_actions

ADD . .

CMD "danger"