# creat a character with pure CSS

멋쟁이 사자처럼에서 진행한 캐릭터 대회 출품작입니다.

HTML과 CSS만을 이용하여 창작캐릭터를 만들었습니다.

https://koreanhamster.github.io/character_contest/

## Preview

![image](https://user-images.githubusercontent.com/95600994/163130745-fa8fa324-8db9-4266-97f1-e44a9d13aa13.png)

## 초반 스케치
![IMG_6921](https://user-images.githubusercontent.com/95600994/163138604-d2a5f59b-4d39-40b9-95ee-652229fb719a.JPG)
**캐릭터 컨셉을 확실히 잡았다.**
- 이름: 바지리 (내가 키우는 바질에서 영감을 받음. 통통하고 연약해보이는데 잘 자란다.)
- 성격: 외유내강을 생각하며 시크하고 세상이 뭐라던 신경쓰지 않는 내 자아를 담았다. 
- 컨셉: 뉴욕시티 / 에어팟프로 / 주머니손 

## 문제점

![Screen Shot 2022-04-13 at 5 47 54 PM](https://user-images.githubusercontent.com/95600994/163137802-8c96644f-3a6d-495a-a42f-3d8e5d7f393a.png)

사진과 같이 캐릭터의 얼굴 정 중앙에 수직선을 활처럼 휘게 만들고 싶었습니다.

## 해결방법

- 사진과 같이 우선 원하는 만큼 border-radius가 들어간 박스를 위치시켜 주고
![Screen Shot 2022-04-13 at 12 51 10 PM](https://user-images.githubusercontent.com/95600994/163133948-8accfcdc-6aee-4488-9bbb-bb9c3bed6f2e.png)
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

- 가상요소로 그와 똑같이 생긴 박스를 하나 더 만들어 교묘하게 제가 원하는 부분만 보여질 수 있도록 위치했습니다.
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
