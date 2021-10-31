FROM python:slim

WORKDIR app
COPY . .
RUN addgroup --gid 1000 non-root && \
    adduser --gid 1000 --uid 1000 non-root --disabled-password --disabled-login --gecos GECOS

USER 1000

EXPOSE 8000
CMD python -m http.server 8000