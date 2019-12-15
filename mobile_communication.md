# 무선이동통신

## CH 4,7 장
### source and channel coding
1. Communication System의 General structure에서 Transmitter의 순서를 쓰시오
> Formatter - Source encoder - Channel encoder - Modulator - Multiplexer
2. Coding theory의 예시를 4가지 쓰시오
> data compression, crytography, error-correction, network coding
3. Source coding의 역할은 무엇인가.
> 데이터를 압축해서 전달을 효과적으로 만들어 준다.
4. Channel encoding의 종류 3가지를 쓰시오
> Read-Solomon, turbo code, LDPC code
5. Channel coding의 역할은 무엇인가.
> 에러를 복구하기위해 redundent data를 추가한다.
6. prefix code의 종류중 하나를 말하고 그것의 coding방식의 평가 지표가 되는 것을 말하시오
> Huffman coding. Variance가 높을수록 좋은 huffman coding이라고 말할 수 있다.
7. FEC는 무엇의 약자인가? 그리고 FEC code의 카테고리를 4개이상 말하시오
> Forward Error correction의 약자
> Block code, Cyclic code, Reed-Solomon code, Convolution code, Turbo code
8. Block code의 data는 k와 r로 나눌 수 있다. 각각이 의미하는 것은 무엇인가?
> k: 원본 데이터, r: redundant data
9. Block code에서 r이 크면 클수록 error를 복구할 수 있는 능력이 커지고 code rate 또한 증가한다. (O/X)
> error를 복구할 수 있는 능력은 커지지만 code rate(k/r)는 감소한다.
10. Block code 예시문제 3장 25page 참고
> 문제 푸는 법 - PHCS
> 1. P - remainder of [x^n-k-1/g(x)]인 P_n구하기 (G=[I|P]를 만들기 위해)
> 2. H - Parity check matrix인 H구하기 (H=[P^T|I])
> 3. C - redundant data가 추가된 codeword 구하기 (c=mG)
> 4. S - error를 체크하는 s 구하기 (s=cH^T)
11. convolution code를 수행하면 데이터의 길이는 몇배가 되는가.
> 2배
12. Shannon limit의 SNR(signal to noise)값은 몇인가. 그리고 Shannon limit가 무엇인지 설명하시오.
> Shannon limit = -1.6 이고 Shannon limit보다 SNR이 좋지 않으면 신호를 보내지 못한다.
13. 잡음이 신호의 1/100인 어떤 전송채널이 있고 대역폭이 2600Hz일 경우 shannon 이론에 따라 capacity 를 구하시오.
> C = 2600log2(1+100)
14. Terbo code는 low-power application을 목적으로 설계되었다. 그렇다면 이것을 사용하는 예시를 4개 이상 쓰시오.
> deep-space, satelite communications, third generation cellular, personal communication service, ad hoc, sensor network
15. modulation의 역할은 무엇이고, 이것이 필요한 이유는 무엇인가.
> 시그널을 변환시켜 주는 것, frequency가 높을 수록 안테나 길이를 줄일 수 있다.
16. Bandwidth의 정의를 3가지 이상 쓰시오.
> 1. Half-power bandwidth
> 2. Noise equivalent bandwidth
> 3. Null-to-null bandwidth
> 4. Fractional power containment bandwidth
> 5. Bounded power spectral density
17. error가 일어나는 원인을 2가지를 쓰시오
> 1. Thermal noise - additive, white, Gaussian Noise
> 2. Inter-Symbol Interference(ISI) - 늦게오는 신호가 방해
18. 다음 중 Digital modulation이 아닌것은?
    1. Frequency Modulation
    2. Frequency Shift Keying
    3. Phase Shift Keying
    4. Quadrature Phase Shift Keying
    5. Quadrature Amplitude Modulation
> 1. Amplitude Modulation(AM)과 Frequency Modulation(FM)은 analog modulation이다.
19.  FM이 AM보다 노이즈에 민감하지 않다. 그 이유는 무엇인가
> FM의 노이즈는 주로 Doppler effect 같은 것에서 나오기 때문에 amplitude(진폭)이 망가지더라도 크게 영향을 받지 않는다.
20. Demodulation의 receivor의 역할이 아닌 것을 고르시오
    1. Improving the SNR using matched filter
    2. Reducing ISI using equalizer(remove channel distortion)
    3. Sampling the recovered waveform
    4. Frequency down-conversion
>정답없음.

20-1. Demodulation의 과정 중 receiveng filter의 역할은 무엇인가.
> 20번의 1번 보기와 같음

20-2. Demodulation의 과정 중 Equalizeing filter의 역할은 무엇인가.
> 20번의 2번 보기와 같음
21. Sinal spase에서 sinal이 원점에 가까울수록 ________이 좋고 ________이 높다.
> 에너지 효율성, 에러 확률
22. Quadrature Amplitude Modulation의 특징이 아닌것은.
    1. 보내는 시그널의 에너지 파워가 다 다르다.
    2. 1000, 1100, 0100, 0000의 에러가 날 확률이 같을 때 에러가 날 확률은 같다. 
    3. 에러가 날 확률은 모두 같다.
    4. AM과 PSK를 combine한 Moudulation방법이다.
> 3. 보내는 시그널의 에너지 파워가 다를 수 있기 때문에 error가 날 확률은 다르다. 

### Multiplexing and MAC
23. 프로토콜의 의미가 무엇인가?
> 통신을 어떻게 진행할지 정하는 규칙(규약)
24. 프로토콜이 진행하는 순서를 말하시오
> Request - indication - reply - confirm
25. 이전 Layer의 SDU는 다음 Layer PDU와 같다 (O/X)
> Layer k's PDU = Layer (k+1)'s SDU
26. OSI 7 Layer를 쓰시오
> Application - Presentation - Session -Transport - Network - Data link - Physical
27. TCP/IP의 4 Layer를 쓰시오
> Application - Transport - Internet - Host to network
28. hybrid referece model의 5 Layer를 쓰시오
> Application - Transport - Network - Data link - Physical
29. 다음중 Combining TDMA and FDMA와 관련없는 하나는?
    1. More robust against frequency selective interference
    2. Much greater capacity with time compression
    3. Inherent tapping protection
    4. Frequency change must be coordinated
> 모두 참
