Flexbox
=======
마지막 수정 : 2020-03-26
(🐸)(https://flexboxfroggy.com)에서 게임으로 연습해보자! (level24만 나중에 다시해보자!)
## 1. Flexbox를 쓰는 이유
- margin-left같은 속성을 두면서 px 값을 주면서 element들의 위치를 바꾸는 것은 XXX! 
- 디바이스마다 화면 사이즈(px)가 다르기 때문에 내가 생각했던 화면대로 안나올 가능성이 엄청 높다.
- 그래서 flexbox가 생겼지롱! 우리는 5가지만 배우면 된다궁

## 2. Flexbox는 어떻게 쓰지?
- 바꾸고 싶은 element의 상위 부모에서 조절한다.(father-child 항상 생각해)
- child의 부모가 항상 붙어있어야 한다. 

```
 .father{
     display:flex;
     flex-direction:
     여기에서 작업을 하면 child에 적용돼!

     justify-content
     align-items 
     같은 속성들!
 }

.child{
    height:
    width: 
    등등
}
```


## Position Property (위치 속성)
### flex-direction : row (horizental이 메인축!)
- default!!
- Main Axis(justify-content) : 가로 
- Cross Axis(align-items) : 세로 

### flex-direction : column (vertical이 메인축!)
- Main Axis(justify-content) : 세로
- Cross Axis(align-items) : 가로


## Child 자체에서 수정하는 속성

### align-self
- child 자체에서 변경
- align-items와 같은 역할이지만, child 한 개의 속성값 바꿀 수 있다.

```
.child:nth-child(2){
    align-self : center
}
```
- 주의할점: 내가 생각한 대로 바뀌지 않고 아무 변화가 없다면 father에 height 값을 주었는지 확인해보쟈'0'

### order
- child 자체에서 변경
- default : 0 
- 순서 바꿀 수 있음 
- -1도 가능하더라 (기본값이 0이니까 가장 앞으로 나오게 할 수 있다.)


### flex-wrap 
- father에서 변경 
- flexbox는 child element 너비를 줄이더라도 element들을 다 한 줄에 들어가게 함!

``` 
flex-wrap : nowrap // 크키 깨더라도 다 한 줄에 유지해!
flex-wrap : wrap // 크기 유지 시켜줘!
```

### align-content
- align-items  vs align-content : https://stackoverflow.com/questions/27539262/whats-the-difference-between-align-content-and-align-items
- align-content는 multiple lines에서 사용! (메인축이 가로라고 했을때, element들의 세로 간격 조절)
- child에 자체에서 수정!
### reverse 라는 것도 있다 어디에서 쓰나!
- flex-direction : row / column / row-reverse / column-reverse
- flex-wrap : wrap / nowrap / wrap-reverse(얜 조금 헷갈림ㅜㅜ)


## responsive design에 좋은 flex grow와 flex shrink!
child 자체!에서 수정
### flex-shrink
- default:1
- 2로 설정해주면 화면 사이즈가 작아지면 다른 것들에 비해 2배로 줄어든다.
- 화면 사이즈 넓어지면 다시 원상태로 돌아온다.(다 사이즈 같겠지?! 따로 설정해준 것이 없다면ㅎㅎ)

### flex-grow
- default: 0
- 만약 공간이 남아있다면 남은 공간을 각자 비율대로 나눠 가져간다. 
- 화면 줄어들으면 사이즈 똑같이 줄어들고, 넓어지면 남은 공간 땅따먹기!
- 2,3.. 으로 크게 설정해도 이미 가져갈만큼 다 가져가면 숫자 커져도 변화 X

## flex-basis
- child 자체에서 수정
- main-aixs sizing
- element에 처음 사이즈 주는 것(초기화 느낌)
- main axis에서 적용
- 변하지 않으면 width나 height 쓰는 거랑 똑같징