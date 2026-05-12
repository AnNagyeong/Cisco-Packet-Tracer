# Cisco Packet Tracer [ 첫 실습 ]  
첫 실습 — PC와 Router 연결 후 Ping 성공  

< 목표 >  
PC와 Router를 연결하고 IP를 설정하여 ping 통신에 성공한다.  

< 사용 장비 >  
Router : 1941  
PC : PC-PT  
케이블 : Copper Straight-Through (또는 Auto Connection)  

1. 장비 배치
Packet Tracer 화면에 Router 1대,PC 1대를 배치하였다.

2. 케이블 연결
Connections 메뉴에서 케이블을 선택 후 연결하였다.  
PC FastEthernet0  
↕  
Router GigabitEthernet0/0  

3. PC IP 설정
PC → Desktop → IP Configuration  
[ 설정값 ]  
IP Address : 192.168.1.2  
Subnet Mask : 255.255.255.0  
Default Gateway : 192.168.1.1

4. Router 인터페이스 설정
Router → CLI  
초기 설정 질문: Would you like to enter the initial configuration dialog?  
입력: no  

이후 아래 명령어 입력:  
enable  // 관리자 모드 들어가기  
configure terminal  // 설정 모드 들어가기   
interface gigabitEthernet 0/0   // 설정할 인터페이스(랜선 꽂는 포트) 선택  
ip address 192.168.1.1 255.255.255.0  // 해당 포트에 IP 주소와 서브넷 마스크를 설정  
no shutdown   // cisco router 인터페이스는 기본적으로 비활성화 상태이기에 명령어를 입력해야 포트가 활성화되며 통신이 가능해진다. 

6. Ping 테스트  
PC → Desktop → Command Prompt  

명령어 입력: ping 192.168.1.1  

결과:  Reply from 192.168.1.1  

PC와 Router 간 통신 성공.  

<img width="1476" height="694" alt="image" src="https://github.com/user-attachments/assets/80cdbc4b-ecbb-4295-84d5-85da127c1e7d" />

