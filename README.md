# testing-distiller

https://github.com/NervanaSystems/distiller

## Setup

build DockerImage and login to container

```bash
$ docker-compose up -d dev
$ docker-compose exec dev bash
```

## Examples

see. [DistillerでDeepLearningのモデルを軽量化: Gradual Pruning編 - tkato’s blog](http://tkat0.hateblo.jp/entry/2018/05/22/082911)

pretraining

```bash
root@1aff972ccdde:/work# cd examples/classifier_compression
root@1aff972ccdde:/work/examples/classifier_compression# python compress_classifier.py --arch simplenet_cifar /work/dataset/data.cifar10 -p 30 -j=1 --lr=0.01
```

finetuning with pruning


```bash
root@1aff972ccdde:/work/examples/classifier_compression# python compress_classifier.py --arch simplenet_cifar work/dataset/data.cifar10 -p 50 --lr=0.001 --epochs=200 --resume=simplenet_cifar/best.pth.tar --compress=simplenet_cifar.schedule_agp.yaml
```

