# Dockerfile

> ```
> FROM alpine:latest
> #安装bin  bash
> RUN apk update && apk add bash
> ENV WORKDIR /app
> COPY ./builds/outputdir/config/ $WORKDIR/config/
> COPY ./rebate.o $WORKDIR
> RUN chmod +x $WORKDIR/rebate.o
> RUN mkdir $WORKDIR/log/
> #RUN tee /logs/rebate.log
> EXPOSE 8014
> #RUN echo "fadsfadf"
> #CMD cat $WORKDIR/config/dev.yaml
> RUN ln -sf /dev/stdout /var/log/rebate.log
> CMD $WORKDIR/rebate.o --serviceId=0 --config=$WORKDIR/config/dev.yaml | tee $WORKDIR/log/rebate.log
> ```



