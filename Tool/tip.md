## brew

```jsx
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

### Node

- node 버전 관리를 위하여 [n](https://github.com/tj/n)을 사용할 것을 권장합니다.
- 현재 10.16.3(v1 SPA) / 12.8.1(v1 node, SSR) / 14.12.0(new) 사용중(2020.12.07 기준)

```jsx
# n 설치
brew install n
# node 원하는 버전 설치
n --version
# 사용
n
```

---

### AWS CLI

```jsx
$ brew install awscli

$ aws configure // key는 레이블스토어 계정 내역 시트 참조바람
AWS Access Key ID [None] : [발급받은 IAM의 Access Key ID]
AWS Secret Access Key [None] : [발급받은 IAM의 Secret Access Key]
Default region name [None] : ap-northeast-2[서울 리전]
Default output format [None] :
```

- [https://docs.aws.amazon.com/ko_kr/cli/index.html](https://docs.aws.amazon.com/ko_kr/cli/index.html) 내용 참고하여 최신버전 사용 권장

---

### **Docker**

Install ***[docker for mac](https://docs.docker.com/docker-for-mac/install/).***

Follow ***[docker guide](https://docs.docker.com/docker-for-mac/#advanced)*** to increase resource limit(need to set memory to 8GB+).

---

### alias

```jsx
vi ~/.zshrc

## 편리한 별칭들  

### aliases
alias k='kubectl'
alias ll='ls -lahg'
alias t='terraform'
alias chrome="/Applications/Google\\ \\Chrome.app/Contents/MacOS/Google\\ \\Chrome"
```

### kubectl

```jsx
### Install with Homebrew on macOS
brew install kubectl
```

### Useful Tools

- 폴더별 환경설정 구분 (brew install direnv)

[direnv - unclutter your .profile](https://direnv.net/)

- k8s context/namespace changer ***[kubectx/kubens](https://github.com/ahmetb/kubectx)***
- Awesome k8s shell prompt ***[kube ps1](https://github.com/jonmosco/kube-ps1)***
- Very cool k8s CLI manage tool ***[k9s](https://k9ss.io/?fbclid=IwAR0MQO9yBF5iKpJlDkuSNtrWGy72zK81I-j071lrKQsV1DLhloOMknOLd64)***