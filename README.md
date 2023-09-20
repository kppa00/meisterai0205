# A. 실시간 처리 신호등

## 개요
   만약 인공지능으로 교통신호를 실시간으로 처리시킨다면 어떨까 라는 생각이 들게 되었고 이렇게 MDP
   주제로까지 선정하게 되었다.

## 동작설명
   1. ( 도로 1 / 도로 2 / 도로 3 / 도로 4 ) 가 있을 때 python Opencv를 이용해서 카메라 영상을 실시간으로
      읽어와, 도로의 자동차를 인식.
   3. 각 도로의 자동차 혼잡도를 각각 측정 후 비교.
   4. 자동차의 혼잡도가 가장 높은 도로의 신호를 먼저 켜줌.
   5. 앞에서 신호를 바꾼 도로를 제외한 두 도로의 자동차 비율을 두 번째로 비교.
   6. 비교를 한 후 자동차 비율이 더 높은 도로의 신호를 켜줌.
   7. 두 번째 비교에서 비율이 낮았던 도로의 신호를 켜줌.
   8. 기다린 횟수는 3번을 초과하지 않음.
   9. 만약 비율이 비슷하다면 기다린 횟수로 비교
__________________________________________________________________________________________________________

# B. 노란 신호등

<img src="https://github.com/kppa00/meisterai0205/assets/136699281/a6baa6e4-1ef3-45ff-a74a-5ad94da06f2e"  width="700" height="370">

## 개요
   딜레마 존(Dilemma Zone)이란 녹색신호에서 황색신호로 바뀌었을 때, 멈추려고 해도 정지선 직전에 멈추는 것이
   물리적으로 불가능하고, 계속 가려고 하면 적색신호로 완전히 바뀐 순간에도 교차로를 빠져나가지 못해
   신호를 불가피하게 위반하게 되는 구간을 의미한다.(여기서 황색 신호에 대해 올바르게 대처하지 않으면 과태료와 벌점이 부과됨)
   하지만 만약 차의 속도, 거리 등을 측정해서 신호가 바뀌는 것을 미리 예고해주는 장치가 있으면 어떨까 생각이 들어 주제로
   선정하게 되었다.
   실제 보행자들의 생각) 신호등이 노란색일 때 그대로 가야할까 or 멈춰야할까 고민

## 동작설명
   1. python Opencv를 이용해서 카메라 영상을 실시간으로 읽어와, 주행중인 자동차 중 정지선과 가장 가까운 자동차를 인식.
   2. 자동차의 속도를 측정.
   3. 황색 신호가 유지되는 시간(최대 5초)을 기준으로 자동차의 크기, 속도로 지나갈 수 있을지, 없을지를 판단.
   4. 지나갈 수 있으면 초록불, 지나갈 수 없으면 빨간불을 점멸.
