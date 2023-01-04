# RabbitMQ

[![CircleCI Build Badge](https://circleci.com/gh/syntasso/promise-rabbitmq.svg?style=shield)](https://app.circleci.com/pipelines/github/syntasso/promise-rabbitmq?branch=main)

This Promise provides RabbitMQ-as-a-Service. The Promise has 3 fields:
* `.spec.env`
* `.spec.plugins`

Check the CRD documentation for more information.


To install, run the following command while targeting your Platform cluster:

```
kubectl apply -f https://raw.githubusercontent.com/syntasso/promise-rabbitmq/main/promise.yaml
```

This will install the RabbitMQ Operator on all the Worker cluster. To verify
that the operator is installed, run the following command while targeting the Worker
cluster:

```shell-session
$ kubectl get deployments.apps
NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
rabbitmq-cluster-operator   1/1     1            1           1m
```

To create a RabbitMQ cluster, run the following command while targeting the Platform cluster:
```
kubectl apply -f https://raw.githubusercontent.com/syntasso/promise-rabbitmq/main/resource-request.yaml
```

To verify that the RabbitMQ cluster is created, run the following command while targeting the Worker cluster:
```shell-session
$ kubectl get rabbitmqclusters.rabbitmq.com
NAME      ALLREPLICASREADY   RECONCILESUCCESS   AGE
example   True               True               1m
```

For further instructions on how to use the RabbitMQ cluster, see the [RabbitMQ
documentation](https://www.rabbitmq.com/kubernetes/operator/using-operator.html#find).

## Development

For development see [README.md](./internal/README.md)

## Questions? Feedback?

We are always looking for ways to improve Kratix and
the Marketplace. If you run into issues or have ideas for us, please let us
know. Feel free to [open an
issue](https://github.com/syntasso/kratix-marketplace/issues/new/choose) or
[put time on our calendar](https://www.syntasso.io/contact-us). We’d love to
hear from you.
