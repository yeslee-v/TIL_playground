# S3 & EC2

## S3(Simple Storage Service)

- 업계 최고의 확장성(Industry-leading scalability), 데이터 가용성(data availability), 보안(Security) 및 성능(performance)을 제공하는 **객체 스토리지 서비스(Object Storage Services)**.
- **파일 서버**의 역할을 한다.

  > 트래픽이 증가하면 그에 따라 장비를 증설하는 일반 파일 서버의 작업을 대행한다.
  >
  > → 트래픽에 따른 시스템적 문제를 고려하지 않아도 된다.

- 파일에 대한 **접근 권한을 지정**할 수 있어 서비스를 호스팅 용도로 사용하는 것을 방지할 수 있다.

- HTTP와 BitTorrent 프로토콜을 지원한다.

  > [BitTorrent](https://www.bittorrent.com/)?
  >
  > - P2P(Peer-to-Peer File Sharing)를 위해 BTT(BitTorrent Token)로 구동되는 통신 프로토콜
  >
  > - 사용자는 인터넷을 통해 데이터를 분산된 방식(decentralized manner)로 배포할 수 있다.

- REST, SOAP 인터페이스를 제공한다.

  > [SOAP(Simple Object Access Protocol)](https://en.wikipedia.org/wiki/SOAP)? 구조화된 정보를 교환하기 위한 메시징 프로토콜 사양

- 여러 시설에서 데이터를 중복으로 저장해 데이터의 손실이 발생할 경우 자동으로 복원한다.
- 버킷에 저장할 수 있는 최대 버킷 사이즈 혹은 최대 객체 수의 제한이 없다.

  > 객체(object)? S3에 저장된 데이터 하나, 하나의 파일
  >
  > 버킷(bucket)? 연관된 객체들을 묶은(grouping) 최상위 디렉토리 → [버킷 생성하기](https://dev.classmethod.jp/articles/for-beginner-s3-explanation/)

- S3 콘솔을 사용해 업로드할 수 있는 최대 파일 크기는 160GB → 더 큰 용량의 파일을 업로드하려면 `AWS CLI`, `AWS SDK` 또는 `Amazon S3 REST API`를 사용한다.

## EC2(Elastic Compute Cloud)

- AWS 클라우드에서 제공하는 확장 가능한 컴퓨터 용량을 제공하는 **원격 컴퓨터**.
- 하드웨어에 투자하지 않고 애플리케이션을 빠르게 개발하고 배포할 수 있다.
- 원하는 대로 가상 서버를 구축하고 보안 및 네트워킹을 구성하여 스토리지를 관리할 수 있다.
- `Scale-up` 또는 `Scale-down`을 통해 트래픽을 예측할 가능성이 줄어든다.

  > `Scale-up`? 기존의 서버보다 높은 사양으로 업그레이드하는 방식으로 **수직 스케일링(vertical scaling)**이라고 부른다.
  >
  > `Scale-down`? 서버를 추가해서 확장하는 방식으로 **수평 스케일링(horizontal scaling)**이라고 부른다.

### reference

- https://docs.aws.amazon.com/ko_kr/AmazonS3/latest/userguide/Welcome.html
- https://docs.aws.amazon.com/AmazonS3/latest/userguide/BucketRestrictions.html
- https://aws.amazon.com/ko/premiumsupport/knowledge-center/s3-large-file-uploads/
- https://www.stitchdata.com/resources/aws-s3/
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html
- https://stackoverflow.com/questions/14392013/what-is-the-difference-between-amazon-s3-and-amazon-ec2-instance
- https://tecoble.techcourse.co.kr/post/2021-10-12-scale-up-scale-out/
