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

대체 가능한 부품이 있다면 대체해도 괜찮습니다. PULSE 반지하랩 포크에서는 가능한 한국 구입처에서 모두 구입하는 것을 목표로 했습니다.


1. IR 센서: Pololu 38 kHz IR Proximity Sensor [구입처](https://www.pololu.com/product/2578)

2. PNP 트랜지스터: 2N3906 : [구입처](https://www.amazon.com/Projects-B-0001-A10f-General-Transistor-92/dp/B07Y3GFR5P/ref=sr_1_6?dchild=1&keywords=2n3906+transistor&qid=1589929461&sr=8-6) 

3. 1 K Ohm 표준 저항 : [구입처](https://www.amazon.com/EDGELEC-Resistor-Tolerance-Resistance-Optional/dp/B07HDDWFDD?ref_=ast_slp_dp) or equivalent

4. 케이스에 맞는 슬라이드 스위치 : [구입처](https://www.amazon.com/gp/product/B07NLR444L/ref=ppx_yo_dt_b_asin_title_o06_s00?ie=UTF8&psc=1) or equivalent

5. 케이스에 맞는 진동 모터 (10×2.0mm 또는 3.4mm) : [구입처](https://www.pololu.com/product/1638)

6. 22 AWG 전선 : W1 – 5 cm; W2 – 4 cm; W3 – 2 cm; W4 – 2 cm

7. 수축 튜브 (납땜 부분 절연 피복용) : 2.5mm 전선용

8. 배터리 홀더: [구입처](https://www.amazon.com/gp/product/B07FL8MFK8/ref=ppx_yo_dt_b_asin_title_o01_s01?ie=UTF8&psc=1) 

9. 3V CR2032 배터리: [구입처](https://www.amazon.com/gp/product/B071D4DKTZ/ref=ppx_yo_dt_b_asin_title_o09_s01?ie=UTF8&psc=1) 

10. 어두운 색의 (검정, 네이비블루, 다크그린 등) 도색재료 (예: 아크릴물감, 유화물감, 매니큐어 등) - 케이스가 어두운 색이 아닌 경우에만 필요 
 
### 펜던트 케이스 만들기

The PULSE pendant case was designed to hold the existing parts. Other pendant designs can be created as desired as long as the IR sensor will fit and has a clear view to the front of the pendant.
 
If not using black material for case, the bottom of the IR emitter will need to be painted black or covered with black electrical tape to absorb any light. If this is not done, the sensor will read false motion and vibrate continuously. Only the flat bottom, do not cover the whole LED.

[Download STL Files](https://github.com/nasa-jpl/Pulse/tree/master/CAD)

![cad_with_parts.jpg](Images/cad_with_parts.jpg)

### 회로도

![Circuit_Diagram.jpg](Images/Circuit_Diagram.jpg)

Central to the design of the PULSE pendant is the infrared sensor unit (U1 in the diagram) that provides a high (~3 V) output signal to pin 3 by default, and drops low (~1 V) when the LED detector (D1) receives a signal indicating your hand (or other reflecting object) is in front of the pendant.  L1 is the radiating infrared LED. When pin 3 goes low, it powers the PNP transistor (Q1) to energize the motor (M1) causing it to vibrate and the pendant to pulse. V1 is the 3 V battery in the case and S1 is the slide switch. Pin 4 on the infrared sensor is an enable input and is not used.

### PULSE 펜던트 조립

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
