FROM ruby:2.5-alpine

LABEL "repository"="https://github.com/duck8823/actions"
LABEL "homepage"="https://github.com/duck8823/actions"
LABEL "maintainer"="<shunsuke maeda> duck8823@gmail.com"

LABEL "com.github.actions.name"="Danger"
LABEL "com.github.actions.description"="Run Danger"
LABEL "com.github.actions.icon"="alert-triangle"
LABEL "com.github.actions.color"="yellow"

RUN apk update \
 && apk add jq \
 && rm -rf /var/cache/apk/*

RUN gem install danger

ADD . .

RUN echo \$GITHUB_EVENT_PATH | jq -r '.number'

CMD ["DANGER_GITHUB_API_TOKEN=\$GITHUB_TOKEN", "danger", "pr", "$(echo \$GITHUB_EVENT_PATH | jq -r '.number')"]