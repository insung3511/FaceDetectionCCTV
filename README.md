# OpenCV_Face_detection_code ✨👩‍💻👨‍💻✨
라즈베리파이 3 를 이용해서 <strong>사람의 얼굴</strong>을 추척 (Tracking) 하는 프로그램이다. openCV라고 하면 여러가지가 있을수 있지만 이 코드는 그저 얼굴을 트레킹 하는 코드 일뿐이다..</br>

# 실행을 하기 위해서 필요한 것들
1. <strong>Raspberry Pi Model B+ 3 👾👾</strong> </br>
~~먹는거 아니다...🍽🍏🍎🍐🍊🍋🍽~~</br> </br>
잠깐 라즈베리파이를 소개를 하자면, 간단히 말하면 초소형 컴퓨터이다. 최근에 출시하는 핸드폰 보단 사양이 떨어져도 가벼운 운영체제 덕에 많은걸 할수 있다.
Raspberry Pi Model B+ 3 모델 외에도 다른 모델을 해도 되지만 이 코드는 Model B+ 3 기준으로 제작이 되었으니 개인적으로 Model B+ 3를 하는걸 추천한다.</br>
<a href="https://www.raspberrypi.org/products/raspberry-pi-3-model-b/"> (링크) </a> </br>

2. <strong>Webcam 📷📸</strong> </br>
웹캠은 딱히 제품이 중요하지 않지만 화질이 좋을수록 좋다. </br>
<a href="http://search.danawa.com/dsearch.php?k1=%EC%9B%B9%EC%BA%A0&module=goods&act=dispMain"> (링크) </a> </br>

3. <strong>Mirco SD Card 16기가 이상 📑📝</strong> </br>
SD 카드도 브랜드가 딱히 중요하진 않은거 같다. 자신이 가지고 있거나 근처 시장에서 판매하는 걸 사용해도 괜찮다. openCV를 설치를 위해서 16기가를 사용한 것이므로 16기가 이상으로 하면 openCV외에 다른 프로젝트를 할게 되면 더 편할수도 있다.</br>
<a href="https://www.amazon.com/SanDisk-COMINU024966-16GB-microSD-Card/dp/B004KSMXVM:"> (링크) </a> </br>

4. <strong>2.1A 충전기 🔌🔋</strong> </br>
Raspberry Pi Model +B 3 같은 경우에는 반드시 2.1A 어뎁터를 사용 해줘야한다. 더욱이나 openCV를 하게 된다면 2.1A를 하지 않으면 나중에 문제가 발생할수 있다. 이  문서에서는 openCV 설치 과정까지 다룬다. 그렇기 때문에 make 과정에서 오류가 안나도록 하기 위해서는 2.1A 충전기를 써야한다. </br>
<a href="http://search.danawa.com/dsearch.php?k1=2.1A%EC%B6%A9%EC%A0%84%EA%B8%B0"> (링크) </a> </br>

5. <strong>모니터 🖥💻</strong> </br>
Raspberry Pi를 할때에는 모니터가 필요하다. Raspberry Pi는 HDMI 밖에 지원이 안되기 때문에 모니터가 HDMI를 지원하다면 더욱이나 좋을 것이다. 자기 집에 있는 TV를 사용해도 되지만 마우스 감도가 좀 이상하게 느껴질수도 있다...</br>
<a href="http://prod.danawa.com/list/?cate=112757&15main_11_02"> (링크) </a> </br>

6. <strong>마우스 및 키보드 ⌨️🖱</strong> </br>
사실...당연히 필요한 물건이지만 그래도 혹시 몰라서 적어놓았다. 이 부분은 따로 링크를 달진 않겠다. 마우스 키보드는 누구나 하나씩은 있을거라고 생각한다...</br>
⚠️⚠️⚠️<strong>마우스는 없더라도 키보드는 반드시 있어야한다</strong>⚠️⚠️⚠️ 

</br>
</br>

# 라즈베리파이 기본 설정
일단을 설치를 위해서 먼저 운영체제를 먼저 설치 해야한다. <a href="https://goo.gl/UxDLHM"> 🍰🍓(라즈비안 다운로드 링크)🍓🍰 </a> </br>
라즈비안 설치 툴은 다 다르지만 나는 <a href="https://etcher.io/"> 💽Etcher💽 </a> 을 이용해서 하였다. </br> 
</br>
라즈비안을 SD 카드에 설치를 완료 했다면, SD카드를 라즈베리파이 안에 넣는다. </br>
그러고 키보드, 마우스, 등 전원을 제외한 필요한 것들을 연결해준다. </br>
필요한 것들을 다 연결했다면 이제 전원을 넣어준다. 처음으로 부팅을 하게되면 좀 오래걸린다. </br>
</br>
부팅이 다 되었다면 먼저 인터넷 설정을 해준다. </br>
인터넷 설정을 다 한후에 본격적으로 <strong>openCV 설치</strong>를 시작할 것이다. 🙌✨

# 라즈베리파이에 openCV 설치하기
나는 <a href="https://goo.gl/wBp591"> 📸 🐍PyimageSearch🐍📸 의 문서</a>를 이용해서 하였다. </br>
openCV 관련 문서들이 많은 사이트 들이다. 혹시 openCV 공부 혹은 프로젝트르 한다면 참고하기 좋은 사이트이다. </br>
</br>
</br>
❗️⚠️❗️⚠️❗️NOTICE❗️⚠️❗️⚠️❗️⚠️ </br>
Python 2.7 버전으로 작성이 된 코드 입니다. openCV 설치 하실때 반드시 주의해서 하세요! 
</br>
</br>

<--! openCV 설치 한글로 작성 예정 -->

# 라즈베리파이에 이 코드 설치 및 실행
<pre>
$ sudo apt-get install git
$ git clone https://github.com/insung3511/OpenCV_Face_detection_code.git
$ cd openCV_Face_detection_code/openCV_EYE/
$ python face_eye_detection.py
</pre>
</br>
설치하고 실행하는데 딱히 문제 될게 없다. 얼굴인식 테스팅 중에 카메라 위치를 옮기지 않아야지 측정이 잘된다. </br>
꼭 참고해서 하길 바란다. 그리고 이 코드는 <strong>라즈베리파이 전용 카메라는 지원하지 않는다.</strong> </br>
라즈베리파이 기본 카메라를 사용할려고 하니, 카메라를 openCV에서 찾질 못했다...</br>

# Contect me

If you have problem about this code, then contect me. </br>
Email : insung.park123@gmail.com  </br>
Facebook : https://www.facebook.com/insung.bahk </br>

If you want to give me some money..Please send here! </br>
Bitcoin : 17qKUu57aUBcvx9T1ea8Ga87EPnDdmwAEP </br>
Ether : 0xdFE8D1536deE8F839Ede7c1f3A0c44116287D931 </br>
Bitcoin Cash : qp90gf09r3y3h06czmtnsfhz9w7s90se4s72vd9pam </br>

</br>
🙇‍♀️👾🤩Thank you! 🤩👾🙇‍♂️
