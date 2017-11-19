FROM python:3.5-alpine
MAINTAINER Kolokotronis Panagiots

# WIP // NOT FOR PRODUCTION !!!

RUN pip install ccpc

ARG VERIFY_SSL
ARG CA_PATH
ARG TOKEN
ARG PROJECT
ARG OWN_NAME
ARG BASE_URL
ARG TIMEZONE

ENV  VERIFY_SSL=$VERIFY_SSL
ENV  CA_PATH=$CA_PATH
ENV  TOKEN=$TOKEN
ENV  PROJECT=$PROJECT
ENV  OWN_NAME=$OWN_NAME
ENV  BASE_URL=$BASE_URL
ENV  TIMEZONE=$TIMEZONE

CMD ccpc -b $BASE_URL -p $PROJECT -t $TOKEN \
`if [ ! -z $VERIFY_SSL ] && [ $VERIFY_SSL=="false" ]; then echo " --no-verify-ssl"; fi` \
`if [ ! -z $CA_PATH ]; then echo " --ca-path $CA_PATH"; fi` \
`if [ ! -z $OWN_NAME ]; then echo " --own-name $OWN_NAME"; fi` \
`if [ ! -z $TIMEZONE ]; then echo " --timezone $TIMEZONE"; fi`
