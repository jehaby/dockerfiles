FROM jehaby/composer

MAINTAINER Stas Makarov <jehaby@ya.ru>

ENV HOME /home/phpbench
RUN adduser -D -g "" -u 1000 -h $HOME phpbench

RUN mkdir /workdir \
    && chown -R phpbench:phpbench /workdir

WORKDIR /workdir
USER phpbench

RUN composer global require phpbench/phpbench
ENV  PATH $PATH:$HOME/.composer/vendor/bin

ENTRYPOINT ["phpbench"]
CMD ["run", "--report=default", "--time-unit=milliseconds", "."]
