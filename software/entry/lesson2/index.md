<br>

<div align="center">
    <h1>Lesson 2. 조종기로 음악을 연주해보아요!</h1>
</div>

<br>

---

<br>


<div align="center">
    <h1>[들어가기]</h1>
</div>

<br>

이번 강의에서는 조종기의 Buzzer를 사용하여 음악을 연주해보려고 합니다. 

페트론 V2의 조종기에는 소리를 재생할 수 있는 Buzzer가 있는데, 주파수별로 소리가 달라서 음계 연주가 가능합니다. 

그리고 빛의 3원색인 RGB(Red, Green, Blue)를 이용하여 다양한 색상으로 조종기의 LED를 빛나게 할 수 있습니다.

 LED 색상을 Buzzer에 맞춰 바꿔보면서 아름답게 음악을 연주해보아요.


<br>

< Buzzer 재생 가능한 음계>

① 옥타브 : 4~8

② 음계 : (각 옥타브별) 도 / 도# / 레 / 레# / 미 / 파 / 파# / 솔 / 솔# / 라 / 라# / 시

<div align="center">
    <h3>빛의 3원색</h3>
    <img src="images/image34.gif" alt="빛의 3원색">
</div>

코딩에서 빛의 3원색 표시 방법

① 컴퓨터는 기계어 2진수로 이해하므로 색상도 2진수로 표시합니다.

② RGB칼라는 8비트를 이용하여 표시하므로 0과 1로 표시할 수 있는 1비트 8개를 이용합니다.


<div align="center">
    <table>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
        </tr>
    </table>
</div>

③ 2<sup>8</sup> = 256 이므로, 8비트를 10진수로 표시하면 범위는 0~255 입니다.

④ 빛을 혼합할 때 혼합한 색이 원래의 색보다 명도가 높아짐으로 가산혼합이라고 합니다. 조명, 컴퓨터 모니터 등에서 사용합니다.

---

<br>


<div align="center">
    <h1>[코드 생각하기]</h1>
</div>

<br>

<h2> 1. 조종기로 음악 연주하기</h2>

다음 “곰 세 마리” 동요를 조종기로 연주해봐요. (저작권 문제로 음계만 표시합니다.)

<div align="center">
    <table>
        <tr>
            <td>가사</td>
            <td>곰 세 마리가 한 집에 있어 아빠곰 엄마곰 애기곰
</td>
        </tr>
        <tr>
            <td>음계</td>
            <td>도 도 도도도 미 솔솔 미도 솔솔미 솔솔미 도도도
</td>
        </tr>
    </table>
</div>

조종기 Buzzer를 재생할 수 있는 블록은 다음과 같이 2가지 종류의 블록이 있는데, 여기서는 음계를 지정할 수 있는 ①번 블록을 사용합니다.

<div align="center">
    <img src="images/image35.png" alt="1">
</div>

<br>

<b>Q, "연주"와 "예약" 블록의 차이점은?</b>

<div align="center">
    <table>
        <tr>
            <td>연주 블록</td>
            <td><img src="images/image36.png"></td>
            <td>선택한 음을 지정한 시간 동안 연주한 후 다음 블록이 실행됩니다. <br>
                연주를 마친 후 다른 동작을 할 때 사용합니다.
            </td>
        </tr>
        <tr>
            <td>예약 블록</td>
            <td><img src="images/image37.png"></td>
            <td>선택한 음을 지정한 시간 동안 연주하되 연주를 시작하면서 바로 다음 블록이 실행됩니다. <br>
                연주를 하면서 동시에 다른 동작을 할 때 사용합니다.
            </td>
        </tr>
    </table>
</div>

<h2> 2. 조종기 LED 색상 변경하기</h2>

조종기의 LED 색상을 음계에 맞춰 다음과 같이 변하도록 해보아요

<div align="center">
    <table>
        <tr>
            <td>도</td>
            <td>레</td>
            <td>미</td>
            <td>파</td>
            <td>솔</td>
            <td>라</td>
            <td>시</td>
        </tr>
        <tr>
            <td><font color="red">빨강</font></td>
            <td><font color="green">초록</font></td>
            <td><font color="blue">파랑</font></td>
            <td><font color="yellow">노랑</font></td>
            <td><font color="pink">핑크</font></td>
            <td><font color="skyblue">하늘색</font></td>
            <td><font color="gray">흰색</font></td>
        </tr>
    </table>
</div>

<br>

<b>Q, LED 관련 블록들의 차이점은?</b>

<div align="center">
    <table>
        <tr>
            <td><img src="images/image38.png"></td>
            <td>색상(7가지)과 밝기(켜기/끄기 포함)를 설정할 수 있습니다.</td>
        </tr>
        <tr>
            <td><img src="images/image39.png"></td>
            <td>RGB(Red, Green, Blue) 색상을 2진수(비트)로 나타내고 서로 색상을 혼합할 수 있습니다. 
            그리고 설정한 색상의 밝기 조절도 가능합니다. <br>
            ①	0b10000000 : Red<br>
            ②	0b01000000 : Green<br>
            ③	0b00100000 : Blue<Br>
            </td>
        </tr>
        <tr>
            <td><img src="images/image40.png"></td>
            <td>RGB 색상의 밝기를(0~255) 각각 조절하여 다양한 색상으로 혼합할 수 있습니다.</td>
        </tr>
        <tr>
            <td><img src="images/image41.png"></td>
            <td>RGB 색상을 혼합하여 만든 6가지 색상을 설정할 수 있습니다.</td>
        </tr>
    </table>
</div>
<br>

---

<br>


<div align="center">
    <h1>[코딩 및 실행하기]</h1>
</div>

<br>

다음과 같이 블록을 조립하여 코드를 만들어봅시다. 

<div align="center">
    <img src="images/image42.png" alt="코드1">
</div>
<div align="center">
    <img src="images/image43.png" alt="코드2">
</div>
<div align="center">
    <img src="images/image44.png" alt="코드3">
</div>
<div align="center">
    <img src="images/image45.png" alt="코드4">
</div>
<br>

다음은 블록에 대한 설명입니다.
<br>
<div align="center">
    <table>
        <tr>
            <td><div align="center"><img src="images/image46.png"><br>
            시작 블록</div></td>
            <td>엔트리의 시작하기 버튼을 클릭하면 코드를 실행합니다. 
            시작 블록의 바로 다음 블록부터 순차적으로 실행됩니다.<br>
            <font color="red"><b>※ 코드 처음에 시작 블록이 없으면 코드는 실행되지 않습니다.</b></font>
            </td>
        </tr>
        <tr>
            <td><div align="center"><img src="images/image47.png"><br>
            조종기 LED 끄기 블록</div></td>
            <td>조종기의 LED가 꺼집니다.<br>
            <font color="red"><b>※ 조종기의 LED를 끄지 않은 상태에서 색상을 변경시키면 색상이 혼합됩니다.</b></font>
            </td>
        </tr>
        <tr>
            <td><div align="center"><img src="images/image38.png"><br>
            조종기 LED(선택) 블록</div></td>
            <td>조종기의 LED가 빨간색으로 켜집니다.
            </td>
        </tr>
        <tr>
            <td><div align="center"><img src="images/image48.png"><br>
            조종기 음계(지정시간) 블록</div></td>
            <td>조종기의 Buzzer에서 5옥타브의 도 음이 0.5초 동안 재생됩니다.
            </td>
        </tr>
        <tr>
            <td><div align="center"><img src="images/image49.png"><br>
            기다리기 블록</div></td>
            <td>0.1초 동안 기다린 후 다음 블록이 실행됩니다. (같은 음이 연속으로 연주될 경우)
            </td>
        </tr>
    </table>
</div>

<br>
이제 코드를 실행해볼까요? 엔트리의 시작하기 버튼을 눌러보아요. 조종기에서 “곰 세 마리” 음악이 잘 연주되나요?
<br>
그런데 만든 코드가 너무 길어서 보기 어려운가요? 그럼 반복문을 사용해서 코드를 줄이고 좀 더 효율적으로 코딩해보도록 해요. 먼저 반복문이 무엇인지 알아볼까요?
<br>
<div align="center">
    <table>
                <tr>
            <td>
                <div align="center">
                    알기 쉬운 코딩
                </div>
            </td>
            <td>
                <div align="center">
                    반복문
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <div align="center">
                    <img src="images/image50.png">
                </div>
            </td>
            <td>
                <div align="left">
                    반복문이란 코딩의 주요 문법 중 하나로서 동일하거나 비슷한 명령을 반복할 때 사용합니다. <br>
                    반복문을 사용하면 코드의 길이를 줄여줘서 코드를 이해하기 쉽게 해줄 뿐만 아니라, 좀 더 다양하고 효율적인 코딩 구현이 가능합니다. 반복문에는 지정한 횟수만큼 반복하기, 무한 반복하기, 특정 조건이 만족할 때까지 반복하기, 이렇게 3가지 종류가 있는데, 각 상황에 맞게 선택하여 사용합니다.
                </div>
            </td>
        </tr>
    </table>
</div>
<div align="center">
    <table>
                <tr>
            <td>
                <div align="center">
                    <img src="images/image51.png"><br>
                    지정한 횟수만큼 반복하기
                </div>
            </td>
            <td>
                <div align="center">
                    <img src="images/image52.png"><br>
                    무한 반복하기
                </div>
            </td>
            <td>
                <div align="center">
                    <img src="images/image53.png"><br>
                    특정 조건이 만족할 때까지 반복하기
                </div>
            </td>
        </tr>
    </table>
</div>
<br>
그럼 반복문을 사용하여 다음과 같이 코드를 수정해보아요.
<br>
<div align="center">
    <table>
        <tr>
            <td>
                <div align="center">
                    <img src="images/image54.png">
                </div>
            </td>
            <td>
                <div align="center">
                    <b>반복문을 사용하여 수정한 코드</b><br>
                    <img src="images/image55.png"><br>
                </div>
                <div align="left">
                    처음 시작하는 부분의 2번째와 3번째 음계 연주하는 코드가 동일하기 때문에 2번 반복하기 블록을 사용하여 위와 같이 코드를 수정할 수 있습니다.<br>
                    반복문을 코딩하는 방법은 반복문 블록 안에 반복되는 코드를 삽입하고 반복 횟수를 설정해주면 됩니다.
                </div>
            </td>
        </tr>
    </table>
</div>

처음 5개 음계 연주하는 코드 부분을 다음과 같이 줄일 수 있습니다.

<div align="center">
    <table>
                <tr>
            <td>
                <div align="center">
                    <img src="images/image42.png"><br>
                    기존 코드
                </div>
            </td>
            <td>
                <div align="center">
                    <h2>→</h2>
                </div>
            </td>
            <td>
                <div align="center">
                    <img src="images/image56.png"><br>
                    수정 코드
                </div>
            </td>
        </tr>
    </table>
</div>

이제 나머지 코드도 반복문을 사용하여 수정하고 전체 코드를 완성해보아요.

<div align="center">
    <img src="images/image57.png" alt="코드1">
</div>
<div align="center">
    <img src="images/image58.png" alt="코드2">
</div>
<div align="center">
    <img src="images/image59.png" alt="코드3">
</div>

<font color="red"><b>※	처음 반복문을 사용하지 않은 코드보다 길이가 많이 줄어든 것을 확인할 수 있습니다.</b></font>

코드를 모두 만들었다면 다시 실행시켜서 연주가 잘 되는지 확인합니다. 연주가 잘 된다면 “곰 세 마리”의 나머지 뒷부분도 코딩하여 곡을 완성해보고 다른 노래 연주도 도전해보아요!
<br>

---

<br>


<div align="center">
    <h1>[정리하기]</h1>
</div>

<br>

눈과 귀가 즐거운 강의였나요? 이번 강의에서 배운 것을 활용하여 자신만의 음악을 만들어서 조종기로 연주해보고, 드론의 LED를 좀 더 화려하게 꾸며봐요.

1. 조종기의 Buzzer를 이용하여 음을 재생할 수 있습니다. (음계 선택 or 주파수)

2. 드론에는 눈과 팔 부분에 LED가 장착되어 있는데, 코딩으로 색상을 변경할 수 있습니다.

3. 드론의 LED 색상을 변경할 때, 이미 LED가 다른 색상으로 설정되어 있다면 색상이 겹쳐지기 때문에 꼭 LED를 먼저 끈 후 변경합니다.<br>
<font color="red"><b>※	색상 겹침을 이용하여 특정 색상을 만들고 싶다면 LED를 끄지 않고 사용합니다.</b></font>

4. 반복문은 동일하거나 비슷한 코드를 반복적으로 수행할 때 사용하고, 코드를 좀 더 간단하고 효율적으로 만들 수 있습니다.

<br>

---

### [엔트리로 코딩해요](../)

 1. [페트론 V2와 엔트리가 만났어요](../lesson1)
 2. **페트론 V2와 인사해요**
 3. [조종기 화면에 그림을 그려보아요](../lesson3)
 4. [조종기로 로봇청소기를 돌려보아요](../lesson4)
 5. [엔트리로 드론을 날려보아요](../lesson5)
 6. [드론으로 센서 놀이를 해보아요](../lesson6)
 7. [센서를 활용한 패턴 비행을 해보아요](../lesson7)
 8. [조종기 버튼으로 드론을 날려보아요](../lesson8)
 
---

Modified : 2019.1.10