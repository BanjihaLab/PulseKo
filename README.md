# PULSE를 한국에서 만들어보자. 
NASA JPL에서 코로나19 감염 방지에 도움을 주기위해 제작한 [PULSE](https://github.com/nasa-jpl/Pulse) 를 한국에서 만들어 봅니다. 

### 차례
* [필요한 도구](https://github.com/BanjihaLab/PulseKo#필요한-도구) 
* [부품 구입](https://github.com/BanjihaLab/PulseKo#부품-구입)
* [펜던트 케이스 만들기](https://github.com/BanjihaLab/PulseKo#펜던트-케이스-만들기)
* [회로도](https://github.com/BanjihaLab/PulseKo#회로도)
* [PULSE 펜던트 조립](https://github.com/BanjihaLab/PulseKo#pulse-펜던트-조립)
* [Acknowledgements](https://github.com/BanjihaLab/PulseKo#acknowledgements)
* [Disclaimer](https://github.com/BanjihaLab/PulseKo#면책사항)


### 필요한 도구

1.	PLA 3D 프린터 (SLA 3D 프린터 모델링은 아직 수정하지 않았습니다. 프린터가 없는 경우에는 부품을 주문해도 좋습니다.)

2. 납땜기, 땜납

3. 전선 스트리퍼

4. 납땜용  (옵션)


### 부품 구입

![Materials_Required.jpg](Images/Materials_Required.jpg)

PULSE 반지하랩 포크에서는 가능한 한국 구입처에서 모두 구입하는 것을 목표로 했습니다. 
크기나 기능이 동일한 대체 부품이 있다면 대체해도 습니다. 


1. IR 센서: Pololu 38 kHz IR Proximity Sensor [구입처1](http://mechasolution.com/shop/goods/goods_view.php?goodsno=8322&category=) 또는 [구입처2](https://www.devicemart.co.kr/goods/view?no=1164601) - [대량 구매시 구입처](https://www.pololu.com/product/2578)

2. PNP 트랜지스터: 2N3906 : [구입처](https://smartstore.naver.com/ic11401/products/620068038) 

3. 1/4w 1K Ohm  저항 : [구입처1](http://mechasolution.com/shop/goods/goods_view.php?goodsno=948&category=) 또는 [구입처2](https://www.devicemart.co.kr/goods/view?no=2014)

4. 수정한 케이스에 맞는 슬라이드 스위치 : [구입처](https://smartstore.naver.com/ic11401/products/628697425?NaPm=ct%3Dkdgvax8m%7Cci%3Dcheckout%7Ctr%3Dppc%7Ctrx%3D%7Chk%3D801e80d3ad9f8f107f6142780b8290a293c08b11) 또는 같은 크기의 제품 - 다른 크기 제품 사용 시 케이스 3D 모델 수정 필요

5. 케이스에 맞는 진동 모터 (10×2.0mm 또는 3.4mm) : [구입처](https://smartstore.naver.com/ic11401/products/578176188?NaPm=ct%3Dkdgvc6mq%7Cci%3Dcheckout%7Ctr%3Dppc%7Ctrx%3D%7Chk%3Db2dab79e1aebe24a11cd3736cb2741df288beb5b)

6. 22 AWG 전선 : W1 – 5 cm; W2 – 4 cm; W3 – 2 cm; W4 – 2 cm

7. 수축 튜브 (납땜 부분 절연 피복용) : 2.5mm 전선용

8. 배터리 홀더: [구입처1](http://mechasolution.com/shop/goods/goods_view.php?goodsno=8322&category=) 또는 [구입처2](https://www.devicemart.co.kr/goods/view?no=1164601)

9. 3V CR2032 배터리: [구입처](https://smartstore.naver.com/ic11401/products/663513466) 또는 가까운 마트 등

10. 어두운 색의 (검정, 네이비블루, 다크그린 등) 도색재료 (예: 아크릴물감, 유화물감, 매니큐어 등) - 케이스가 어두운 색이 아닌 경우에만 필요 
 
### 펜던트 케이스 만들기

PULSE 펜던트 케이스는 부품을 잘 모아서 고정해줄 수 있도록 설계한 것입니다. IR 센서가 잘 고정되고, 펜던트 앞 부분이 잘 뚫려 있다면 다른 디자인으로 만들어도 좋습니다. 

케이스 재료가 어두운 색이 아니라면, IR Emitter의 아래쪽에 (빛을 흡수하는) 검정색으로 칠하거나 검정 절연 테이프를 붙여 주세요. 그래야 센서의 오감지가 줄어듭니다. 주의할 점은 평평한 아래부분만을 칠하는 것이지, 전체 LED를 칠하면 안 된다는 점입니다.

[한국버전 STL 파일](https://github.com/BanjihaLab/PulseKo/tree/master/CAD/FDM)

아직 FDM 버전만 수정되었습니다. SLA 버전은 차후 업데이트 예정입니다.

![cad_with_parts.jpg](Images/cad_with_parts.jpg)

### 회로도

![Circuit_Diagram.jpg](Images/Circuit_Diagram.jpg)

PULSE 펜던트에서 가장 중요한 것은 적외 (infrared) 센서입니다. (회로도의 U1) 이 센서는 기본적으로 pin 3에 높은 (~3V) 출력 신호를 내지만, LED 검출기(detector; D1)가 (다른 반사체인 경우도 있겠지만) 여러분의 손이 펜던트 앞에 있다는 신호를 받으면 낮은 출력 (~1V)으로 신호 강도가 떨어집니다. L1은 적외선을 방출하는 LED 입니다. pin 3의 출력이 낮아지면, PNP 트랜지스터 (Q1)가 진동모터 (M1)에 전력을 공급하게 되고, 펜던트가 진동하게 해줍니다. V1은 3V 배터리를 케이스에 넣은 것이고, S1은 슬라이드 스위치입니다. IR 센서의 Pin 4는 IR 방출기 작동을 컨트롤하는 핀이지만 사용하지 않습니다.

### PULSE 펜던트 조립

아래의 원래의 조립 설명서와 함께 [링크](https://banjihalab.com/covid-19_pulse_pendant-2)를 참조해서 조립해주세요.

1. Wire W1 solders to the center pin of the switch and wire W2 solders to an end pin of the switch. The third pin on the switch can be 		clipped off – it is not used. Heat shrink covers the pins. This picture shows the completed switch next to an assembled PULSE pendant

![assembly_step_1.jpg](Images/assembly_step_1.jpg)

2. The other end of W2 solders to the emitter pin of the transistor as well as wire W3. (This is a three-way connection – wires W2, W3 		and the transistor emitter pin are connected together; this is the positive voltage). The picture shows the use of a helping hands to 	perform the soldering of three leads, and then the end result. Heat shrink is used to cover the lead at the transistor.

![assembly_step_2.jpg](Images/assembly_step_2.jpg)

3. The other end of wire W3 then attaches to pin 2 of the IR sensor

4. Wire W4 (ground), attaches to pin 1 of the IR sensor

5. The 1 K Ohm standard resistor attaches to the middle or base pin of the transistor. Use heat shrink to cover the connection

6. The 1 K Ohm standard resistor attaches to pin 3 of the IR sensor. This picture shows the assembly so far

![assembly_step_5.jpg](Images/assembly_step_5.jpg)

7. The red wire of the vibrating motor solders to the collector pin of the transistor. Use heat shrink to cover the connection

![assembly_step_6.jpg](Images/assembly_step_6.jpg)

8. The black wire of the vibrating motor solders to the ground port of the battery case (jointly with W4). The other end of W1 solders 		to the positive pin of the battery holder. This picture shows the completed assembly and the wires folded for insertion into the 				bottom case

![assembly_step_7.jpg](Images/assembly_step_7.jpg)

9. The motor and switch snap into the case base

10. The IR sensor slides into the case base rails

11. The electronics are gently tucked into the case base

![assembly_step_10.jpg](Images/assembly_step_10.jpg)

12. Using a dark colored paint (i.e., acrylic, oil, nail polish etc.) such as black, navy blue, dark green, etc., lightly paint over the 		emitter as shown in the image below. Using a dark colored pen or marker will not work the same as paint. 

![assembly_step_11.jpg](Images/assembly_step_11.jpg)

13. With the electronics in the case base, the battery can be installed, the switch can be set on; move your hand in front of the IR 				sensor and the red LED on the sensor board will light and the case will PULSE!  

[![GitHub_Video_Thumbnail.jpg](Images/Misc/GitHub_Video_Thumbnail.jpg)](https://www.youtube.com/watch?v=7utCPXKdKHg&list=PLKWlaxzCh8uKqaNQIiBa6WjCEDBVH6ehV&index=3)

14. Install the top case. Attach a necklace of your choice and PULSE is complete


### Acknowledgements
PulseKo는 [반지하랩](https://banjihalab.com)에서 NASA JPL의 [Pulse](https://github.com/nasa-jpl/Pulse)를 한국에서 제작해보기 좋도록 만들어 보고 그 방법을 공유하기 위한 프로젝트입니다.


##### Ackowldgements [[link]](https://github.com/nasa-jpl/Pulse#acknowledgements)
In early March of 2020, it was becoming quite apparent that the pandemic has reached the United States. We, like so many other countries, would have to partake in precautionary methods to protect ourselves from contracting a novel virus that was affecting the world in unrecognizable ways.  

With little information available, we turned to the CDC for guidance. They provide the general public with a clear list of tasks to help prevent infection, one of which was advising us not to touch our faces. As the news unfolded and the warnings heightened, we found ourselves immersed in discussions related to the topic, most of which consisted of commiserating on the laborious task of not touching our face. During a Monday morning tag-up, and as our team members revealed how often they touch their face, [Tom Cwik](mailto:pulse@jpl.nasa.gov), the engineer, and [Faith Oftadeh](mailto:pulse@jpl.nasa.gov), the designer, suddenly realized that a simple wearable device may help with this problematic subconscious behavior. 

Immediately, we started pulling together a list of inexpensive and easily accessible parts, sketching out ideas, and once the concept seemed plausible, we agreed to pursue it all while JPL closed and transitioned to telework. Within days, we found ourselves adjusting to a new way of living. While working from home, managing childcare, and attempting to do “business as usual,” we continued developing PULSE via text and Facetime during the nights and weekends. When it came to creating a proper casing for the pendant, Dan Kolenz joined the team as the CAD mechanical designer. After prototyping and working through sluggish online parts ordering, coupled with frequent late-night texting, facetime sessions, and 3D printing in the garage, we managed to create an operating prototype.  

Dave Gallagher, JPL’s Associate Lab Director provided significant encouragement and JPL support to move forward. Rafael Martinez paved the way from within JPL to allow us to release PULSE and bring it to where it is today. Lisa Harbottle volunteered to demo and model the pendant, Gary Bolotin gave a review of the electronics, Kristy Kawasaki designed the website, and Olivia Cwik was key to soldering and added to the Readme.

Our goal was to create a simple device that can help minimize the spread of a virus. We also hope that the public can further develop this concept. As we return to our office spaces and attempt to integrate back into society, we believe that PULSE may help others stay as healthy as possible.


### 면책사항
반지하랩은 Pulse의 작동이나 효과에 대해 보증할 수 없습니다. 아래의 NASA JPL의 Disclaimer를 확인해주세요.

##### Disclaimer [[link]](https://github.com/nasa-jpl/Pulse#disclaimer)

Disclaimer: The designs herein have not been reviewed, cleared, or approved by FDA or other regulatory authority, nor have they received Coronavirus Disease 2019 (COVID-19) Emergency Use Authorizations for Medical Devices. Neither California Institute of Technology (including the Jet Propulsion Laboratory)("Caltech") nor its employees or agents provide any representation or warranty, express or implied, for fitness for a particular purpose, safety, efficacy, or non-infringement of any third party intellectual property rights. Caltech offers these device designs in good faith to help healthcare providers and others prevent the spread of and treat patients with COVID-19. Physicians and other healthcare providers bear full responsibility to convey warnings and obtain patients' informed consent.

##### The research was carried out at the Jet Propulsion Laboratory, California Institute of Technology, under a contract with the National Aeronautics and Space Administration.
