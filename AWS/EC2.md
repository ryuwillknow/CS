# EC2

[https://inpa.tistory.com/entry/AWS-📚-EC2-개념-사용-구축-세팅-💯-정리-인스턴스-EBS-AMI](https://inpa.tistory.com/entry/AWS-%F0%9F%93%9A-EC2-%EA%B0%9C%EB%85%90-%EC%82%AC%EC%9A%A9-%EA%B5%AC%EC%B6%95-%EC%84%B8%ED%8C%85-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC-%EC%9D%B8%EC%8A%A4%ED%84%B4%EC%8A%A4-EBS-AMI)

[https://inpa.tistory.com/entry/AWS-📚-자주-쓰이는-aws-네트워킹-클라우드-용어-정리](https://inpa.tistory.com/entry/AWS-%F0%9F%93%9A-%EC%9E%90%EC%A3%BC-%EC%93%B0%EC%9D%B4%EB%8A%94-aws-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%82%B9-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)

Amazon Elastic Compute Cloud = EC2

EC2는 복잡한 공유기 세팅없이 인터넷을 통해서 자유롭게 접속할 수 있고, **이미지(AMI) 기능**도 사용할 수 있다

이 OS 상태 그대로 저장하는 기능을 이미지(AMI) 라고 한다

instance : 컴퓨터

EBS : 하드디스크

ENI : 랜카드

m5a.large

인스턴스 타입, 세대, 접두사

EBS와 LocalStorage 두가지 방식이 있다.

free tier 는 t2.micro 밖에 안된다 ㅠㅠ

### 인스턴스 생성하기

AMI ⇒ 인스턴스 서버의 운영체제를 선택하는 것, 우분투 or 리눅스

VPC는 아직 안 배워서 기본값으로 둔다.

가상스토리지 (EBS)는 여러 옵션이 있다. 종료시 삭제도 가능, 볼륨유형이 종류이다.

## SSH연결 하기 하면 EC2바로 연결 가능 보안그룹 추가가 필요할 뿐

EC2 SSH연결하기 putty 사용

pem은 puttygen으로 변환시켜야한다.

키페어 생성하고 그 파일을 잘 갖고 있어야한다.

보안그룹 인바운드 규칙을 추가해야한다?? 들어오는 규칙!!

cidr 0.0.0.0/0 이면 모든 ip를 허용한다는 것이다. 22번포트는 SSH이다!

### 인스턴스 시작

시작버튼 누르고 연결 or SSH putty를 통해 연결해서 터미널을 띄운다.

**탄력적 IP** 라는 것을 설정 해주어야 하는데, 이 인스턴스에서 설정된 **퍼블릭 IP**는 **서버를 키고 끌때마다 새로운 것으로 갱신**되기에, 이를 하나의 IP로 통일(고정)하기 위함이다.

안 그러면 인스턴스 끄고 킬때마다 아이피가 바뀌는 불상사가 일어난다.

이 한계를 알고 나중에 서비스할 때 참고하자. 

### 이미지 다루기

잘 빌드된 백앤드 어플리케이션을 AMI로 만들뒤 오토스케일링이나 로드 밸런싱에서 인스턴스를 사용할때, 미리 만들어든 AMI을 사용한다면 시간을 많이 절약 할 수 있게 된다. 이미 준비된 상태로 인스턴스를 실전 배치를 할 수 있기 때문이다.
