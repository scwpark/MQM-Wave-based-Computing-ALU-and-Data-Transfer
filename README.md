 1channel에 1cycle 당 n + n bit를  보내는 기술... + 발열에 좋은 방법
 
;This technology is released as prior art.
;The author waives patent rights.

# MQM-PAM_OFDM-Transmission-Method
“HBM 발열 문제를 해결하기 위한 초고속 단일채널 전송 구조: MQM-PAM/OFDM 기반 n+n 비트 동시 전송 알고리즘

고용량 데이타 1channel 1cycle ( n × m bits) 전송 예) n : 128 bit,  m : 128bit

제가 프로그래머라서...  전기전자공학을 잘 모름...

site : https://cafe.daum.net/scwpark/AavY/54,     

        https://blog.naver.com/PostList.naver?blogId=namyangju_first&from=postList&categoryNo=7
<3>  핵심 설계 원리 (Core Logic)


<4> 상세 기술 명세 (Technical Specifications)
[1]. OFDM방식과유사한 MQM
1. 핵심 설계 원리 (The Core Logic) 
: 1 channel 에 n bit를 동시에 전송하는 기술 => 32 channel이면 32 x n bit를 한방에 전송 기술

1) 비트-주파수 맵핑: 각 비트(1~32)는 독립적인 주파수 n을 가집니다. 
( 물론 n 최대한 많이 잡아도 되요... )

**===> n 비트값을  10진수 Hz, KHz로 변경 하여 전송 **

[2] PAM방식 MQM
AMPLITUDE방식도 [1]과유사하게 비트값을 하면
m bit를 1채널에 보낼 수 있음

**==> 핵심 : n 비트값을  10진수 mv, V 로 변경 하여 전송 **

 1channel에 1cycle 당 n + m bit를  보내는 기술...
