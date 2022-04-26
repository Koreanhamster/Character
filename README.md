Web 캐릭터 경진대회 출품작(우수상)
===
URL: https://koreanhamster.github.io/character_contest/
![image](https://user-images.githubusercontent.com/95600994/163130745-fa8fa324-8db9-4266-97f1-e44a9d13aa13.png)

## 기술 스택
- HTML
- CSS

## 초반 스케치
![IMG_6921](https://user-images.githubusercontent.com/95600994/163138604-d2a5f59b-4d39-40b9-95ee-652229fb719a.JPG)
- 이름: 바지리 (키우는 바질에서 영감을 받음. 통통하고 연약해보이는데 잘 자란다)
- 성격: 외유내강을 생각하며 시크하고 세상이 뭐라던 신경쓰지 않는다.
- 주요컨셉: 뉴욕시티 / 에어팟프로 / 주머니손 

## 부딪힌 문제점

![Screen Shot 2022-04-13 at 5 47 54 PM](https://user-images.githubusercontent.com/95600994/163137802-8c96644f-3a6d-495a-a42f-3d8e5d7f393a.png)

- 사진과 같이 캐릭터의 얼굴 정 중앙에 수직선을 활처럼 휘게 만들고 싶었다.
- 그냥 얇고 기다란 선을 만들고 각도를 조절하는건 쉬웠지만, 저렇게 활처럼 휘어보이는 표현은 어떻게 해야할 지 막막했다. 검색 중 border-radious를 준 다음 나머지 변을 tranparent로 처리하는 방법을 발견했지만, 실력의 한계로 막혔다.
- 시도하려고 했었던 기술 링크 https://jsfiddle.net/jonataswalker/s3vd2hny/

## 해결방법

![Screen Shot 2022-04-13 at 12 51 10 PM](https://user-images.githubusercontent.com/95600994/163133948-8accfcdc-6aee-4488-9bbb-bb9c3bed6f2e.png)



- 사진과 같이 우선 원하는 만큼 border-radius가 들어간 박스를 위치시켜 주고
```
.line-vertical {
  position: absolute;
  top: 32px;
  left: 133px;
  width: 85px;
  height: 361px;
  background-color: #feffde;
  border: 5px solid #feffde;
  transform: rotate(17deg);
  border-radius: 140% 10% 0 100%;
  opacity: 20%;
}
```

- 가상요소로 그와 똑같이 생긴 박스를 하나 더 만들어 교묘하게 원하는 부분만 보여질 수 있도록 위치했다.

![Screen Shot 2022-04-13 at 5 37 19 PM](https://user-images.githubusercontent.com/95600994/163136061-d3de730d-c2c3-4c00-8513-535e5e5b0962.png)

```
.line-vertical::after {
  position: absolute;
  content: "";
  display: block;
  top: -7px;
  left: 1px;
  width: 85px;
  height: 365px;
  background-color: #91c788;
  border: 5px solid #91c788;
  border-radius: 140% 10% 30% 120%;
}
```

- 계기일식의 초승달과 같다고 생각하면 된다.
![Screen Shot 2022-04-13 at 5 39 19 PM](https://user-images.githubusercontent.com/95600994/163136168-c7092c40-f2ac-4b96-8faf-c051c233e91f.png)

출처: 연합뉴스

## What I learned..

- 사실 비슷한 속성을 가진 여러 요소들(예를들면 얼굴 안의 가로선이나, 에어팟, 양 팔 다리 등)은 애초에 중복되는 값을 한번에 주고 각각 개별요소에만 다른 속성을 따로 줬다면 코드가 훨씬 간결하고 효율적이었을텐데, 처음 만들다 보니 전혀 그를 고려하지 못하고 구현에만 급급했다. 모든 코드를 작성한 후에야 비슷한 요소들을 묶어주려 시도했으나 구현이 갑자기 이상하게 되는 등 생각처럼 쉽지 않았다. 

- 이를 통해 '기초 설계'가 얼마나 중요한지 깨달았다. 러프한 스케치만 해놓고 무작정 시작했었던게 원인이었다. 스케치 이후에 어떤 요소를 어떤식으로 구현할 것인지. 또 이 요소들은 중복되는 속성이 많은데 어떻게 효율적으로 짤 것인지 탄탄하게 설계해놓고 시작하는게 결국에 시간절약과 코드퀄리티 향상으로 이어짐을 배웠다.

## 추가: WEB 캐릭터 디자인 경진대회 우수상 수상

![Screen Shot 2022-04-20 at 9 06 43 PM](https://user-images.githubusercontent.com/95600994/164226909-09be3cf0-d587-4d6a-b9bd-66e3231ff982.png)


70여명의 경진대회 참가자 중에서 우수상을 수상하였습니다.
더 즐겁고 열심히 코딩하라는 뜻으로 감사히 받겠습니다!

