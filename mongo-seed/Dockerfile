FROM mongo:5.0.22

ARG DATABASE_URI
ARG USERNAME
ARG PASSWORD

ENV DATABASE_URI ${DATABASE_URI}
ENV USERNAME ${USERNAME}
ENV PASSWORD ${PASSWORD}

COPY ./sample_analytics/accounts.json /accounts.json
COPY ./sample_analytics/customers.json /customers.json
COPY ./sample_analytics/transactions.json /transactions.json

CMD mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection accounts --drop --file /accounts.json \
    && mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection customers --drop --file /customers.json \
    && mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection transactions --drop --file /transactions.json


