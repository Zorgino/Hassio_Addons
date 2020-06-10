ARG BUILD_FROM
FROM $BUILD_FROM AS BUILD

ENV LANG C.UTF-8
ENV COMMIT_SHA '6e4e2dffff745ef3275c14e33d90038010afca60'

RUN apk add --no-cache git=2.24.3-r0 npm=12.15.0-r1
# hadolint ignore=DL3003
RUN git clone https://github.com/rand256/valetudo-mapper -b master /app && \
    cd app && git checkout $COMMIT_SHA

WORKDIR /app
RUN npm install

COPY run.sh /
RUN chmod a+x /run.sh
CMD [ "/run.sh" ]
