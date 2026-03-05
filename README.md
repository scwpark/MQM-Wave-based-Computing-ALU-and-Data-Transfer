# MQM-PAM_OFDM-Transmission-Method
“HBM 발열 문제를 해결하기 위한 초고속 단일채널 전송 구조: MQM-PAM/OFDM 기반 n×n 비트 동시 전송 알고리즘

고용량 데이타 1channel 1cycle ( n × m bits) 전송 예) n : 128 bit,  m : 128bit

제가 프로그래머라서...  전기전자공학을 잘 모름...

site : https://cafe.daum.net/scwpark/AavY/54,     

        https://blog.naver.com/PostList.naver?blogId=namyangju_first&from=postList&categoryNo=7
<3>  핵심 설계 원리 (Core Logic)
1) 비트-주파수/전압 매핑: 1개의 채널에 n-bit 데이터를 동시에 전송하며, 
각 비트는 독립적인 주파수와 전압을 가집니다. 
2)  수열 적용: 주파수와 전압의 간격은 f(n) = f(n-2) + f(n-1) + m (m=1 등) 형태의 수열을 
통해 결정되어, 데이터 중첩 시에도 완벽한 무결성을 보장합니다

<4> 상세 기술 명세 (Technical Specifications)
[1]. OFDM방식과유사한 MQM
1. 핵심 설계 원리 (The Core Logic) 
: 1 channel 에 n bit를 동시에 전송하는 기술 => 32 channel이면 32 x n bit를 한방에 전송 기술

1) 비트-주파수 맵핑: 각 비트(1~32)는 독립적인 주파수 n을 가집니다. 
( 물론 n 최대한 많이 잡아도 되요... )


2진수 값 
(Binary)	해당 비트 조합	MQM 계산식 (Hz)	최종 주파수 (Hz)	비고
0	없음	0	0 Hz	신호 없음 (Ground)
1	1st bit	2	1 Hz	기초 주파수
10	2nd bit	3	2 Hz	제2 채널
11	1st + 2nd	5	3 Hz	주파수 중첩 시작
100	3rd bit	6	4 Hz	상태 비트(+1) 적용
101	1st + 3rd	8	5 Hz	복합 파형 1
110	2nd + 3rd	9	6 Hz	복합 파형 2
111	1st+2nd+3rd	11	7 Hz	풀 비트 중첩
1000	4th bit	12	8 Hz	상태 비트(+1) 재적용


[2] PAM방식 MQM
AMPLITUDE방식도 [1]과유사하게 비트값을 하면
n bit를 1채널에 보낼 수 있음
2진수 값
 (Binary)	해당 비트 조합	MQM 계산식 
(mV)	최종 전압
 (mV)	비고
0	없음	0	0 mV	신호 없음 (Ground)
1	1st bit	2	2 mV	기초 전압 설정
10	2nd bit	3	3 mV	제2 채널 활성화
11	1st + 2nd	2 + 3	5 mV	전압 중첩 시작
100	3rd bit	6	6 mV	상태 비트(+1) 적용
101	1st + 3rd	2 + 6	8 mV	복합 전압 파형 1
110	2nd + 3rd	3 + 6	9 mV	복합 전압 파형 2
111	1st+2nd+3rd	2+3+6	11 mV	1그룹 하위 풀 비트 중첩
1000	4th bit	12	12 mV	상태 비트(+1) 재적용
