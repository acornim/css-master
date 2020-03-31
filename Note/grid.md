Grid
=======
마지막 수정 : 2020-03-31

## Grid 쓰는 이유
- flexbox에서 grid 만들기가 어렵기 때문! flexbox에서 나누고 옮기고 element들을 중간에 두는 건 쉬운데..ㅜㅜ
- father에서 grid design 하기!

### grid 만들기
- grid-template-columns : width 사이즈 정하기 
- grid-template-rows : height 사이즈 정하기 
```
// 내가 원하는 만큼 column 갯수만큼의 사이즈 적기 
// 만약 내가 작성한 것보다 elememt가 그 이상이라면 다시 첫번째부터 반복
grid-template-columns : 20px 55px 100px
```

### Gap
- column-gap 
- row-gap
- shortcut: gap 
- height 지정안해주면 font 사이즈만큼 

## template-area

### repeat 아주 유용한 function!! 잊지마! 너 베프!
- grid-template-columns : repeat(4,200px) 

### grid-template-area
- 눈에 보이게 레이아웃 디자인 하는 방법
- 비우려면 . 찍기
- html에서 클래스네임은 정해놨지만 grid는 몰라서 아무것도 안해. 그래서 grid-area로 이름 정해줘야돼!
- grid-area : header ; // child자체에서 지정
```
"header header header header"
"content content content nav"
"content content content nav"
"footer footer footer footer"
```

### line으로 어디서 시작하고 어디서 끝날지 정해보쟈 :3
- grid-column-start
- grid-column-end
- shortcut : grid-column : start / end ; 
- 1 2 3 ... 은 left부터 세는 것
- -1 -2 -3 ... 은 right부터 세는 것

#### 더 쉬운 shortcut! span!
- ㄹㅏ인 하나하나 다 세기 귀찮으니까 span 사용!
- 몇 개 셀 가지고 있는 지 적어주기 
- grid-column : span 4;

### Line naming
- ref :  https://www.smashingmagazine.com/2017/10/naming-things-css-grid-layout/ 
- 나는 잘 안씀... 

### super shortcut! gird-templete !! (area 안붙음 근데 비슷해)
1. grid-area 정하기 (child에 하는 거 잊지 않았지?)
2. 당연히 grid-template-columns / rows는 삭제
3. grid-template-area랑 비슷하지만, row, height 사이즈 정해줄 수 있어! 짱 편해 + 네이밍도 가능ㅎㅎ
- repeat 은 적용 안돼ㅜㅜ

```
 [header-start] "header header header header" 1fr(row-height) / 1fr 1fr 1fr 1fr(column-width) [header-end]
```

## Place items 
### item과 content의 차이점은?
- item은 셀 하나하나에 적용 
- content는 whole grid에 적용

### justify-items (수평width) 
- strech 가 default / start, center, end
- grid container는 grid 가지고 있고 children 늘려서 자기자신 칠하게

### align