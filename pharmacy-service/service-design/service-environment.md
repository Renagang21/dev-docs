### Amazon Lightsail 서버 구성

1. **Lightsail 인스턴스 생성**:
    - Linux/Unix
    - Node.js 
    - 2GB RAM, CPU:2 , 60GB SSD, 전송:3TB
    - 인스턴스 이름: phamacy-automation
### pharmacy-automation 인스턴스 
- 리전:서울(ap-northeast-2)
- 사용자 이름: bitnami
- publish IPv4 주소 : 3.36.29.195
- private IPv4 주소  : 172.26.2.78
- 고정 IP:  pharmacy-static-ip


**도메인 설정**:
	- 가비아 네임서버 변경
	    - ns-85.awsdns-10.com  
		- ns-809.awsdns-37.net  
		- ns-1037.awsdns-01.org  
		- ns-1886.awsdns-43.co.uk
	- Route 53 -> DNS 영역 생성
	[[Pasted image 20250313110634.png]]
	
**[[Node.js 애플리케이션 실행 방화벽 설정 확인]]**
	 
	 
	  
3. **서비스 환경**:
    - Nginx 웹 서버
    - PM2 프로세스 매니저 설치
    - 데이터베이스: PostgreSQL

