# 9주차 사전 모델을 이용한 MNIST 손글씨 분류

본 과제에서는 수업시간에 배운 사전학습된 CNN을 이용하여 1차원 MNIST 손글씨 데이터를 분류합니다.

## 코멘트
베이스라인은 사전학습된 "CNN"으로 측정되었습니다. 참고해서 코드 작성해주시길 바랍니다.
베이스라인으로 사용된 사전학습 CNN network는 아래와 같이 사용하시면 됩니다.
    import torchvision.models as models

    if method == "resnet":
        model = models.resnet18(pretrained=True)
        model.fc = torch.nn.Linear(in_features=512, out_features=10, bias=True)
    elif method == "vgg":
        model = models.vgg16(pretrained=True)
        model.classifier[6] = torch.nn.Linear(in_features=4096, out_features=10, bias=True)
    elif method == "alexnet":
        model = models.alexnet(pretrained=True)
        model.classifier[6] = torch.nn.Linear(in_features=4096, out_features=10, bias=True)
    else:
        raise ValueError("Check Method!")
## 베이스라인 관련 공지
베이스라인을 달성하기 위해 아래와 2가지의 변환이 사용되었습니다.

### [1] Image Resize
28x28 MNIST 이미지를 224x224 로 resize하여 모델의 input으로 사용하였습니다.

    import cv2
    cv2.resize(x_data[index], dsize=(224, 224), interpolation=cv2.INTER_LINEAR)
### [2] Transform
그동안 sklearn에 있는 다양한 Scaler를 사용하여 데이터를 normalization 했던 것처럼 이미지 역시 normalization을 해주는요, 아래와 같은 Transform을 적용하였습니다. (0.485, 0.456, 0.406) 그리고 (0.229, 0.224, 0.225) 는 ImageNet 데이터셋의 평균과 표준편차로 흔히 사용되는 값입니다.

    transform = transforms.Compose(
        [transforms.ToTensor(),
        transforms.Normalize((0.485, 0.456, 0.406), (0.229, 0.224, 0.225))])
## Evaluation
손글씨(0-9 사이의 정수)를 예측하는 분류 문제로, Accuracy(정확도) Score로 평가