# 리액트 공부

## 컴포넌트 생성
사용자가 볼 수 있는 요소들은 컴포넌트로 구성
컴포넌트의 기능은 단순한 템플릿 이상이고 데이터가 주어졌을 때 이에 맞추어 UI를 만들어 주는 것은 물론이고 컴포넌트가 화면에서 변화할때 주어진 작업들을 처리할 수 있으며, 메서드를 만들어 특별한 기능을 붙일 수 있다.

## 컴포넌트를 만드는 방법
1. 파일만들기
2. 초기 코드 작성하기
3. 모듈 내보내고 불러오기

### 컴포넌트 속성
#### props

props는 properties를 줄인 표현으로 컴포넌트 속성을 설정할 때 사용하는 요소 입니다.
이는 컴포넌트를 가져와서 사용하는 부모 컴포넌트 에서만 설정할 수 있다.

#### 순서
1. props 렌더링 하기
2. props 값 설정하기
3. props 기본값 설정하기
4. props 값 검증하기 

```javascript
MyComponent.js

import React, { Component } from 'react';
import PropTypes from 'prop-types';

class MyComponent extends Component {
    ...
    // 3. 기본값 설정하기
    static defaultProps = {
        name: 기본이름,
        age: 3
    }
    // 4. props 값 검증하기
    static propTypes = {
        name: PropTypes.string, // string 타입을 문자열로 설정합니다.
        age: Proptypes.number.isRequired
    }

    //1. props 랜더링 하기 
    render(){
        return(
            <div>
                안녕하세요, 제 이름은 {this.props.name} 입니다.
            </div>
        )
    }
}

export default MyComponent;
```
```javascript
App.js

import React, {Component} from 'react';
import MyComponent from './MyComponent';

class App extends Component{
    //2. props 값 설정하기 
    render(){
        return(
            <MyComponent name='React' age={3} />
        );
    }
}

export default App;
```

## state
 props는 부모 컴포넌트가 설정하여 컴포넌트 자신은 해당 props를 읽기전용으로만 사용할 수 있습니다. 컴포넌트 내부에서 읽고 업데이트 할 수 있는 값을 사용하려면  state를 써야합니다. 이것은 언제나 기본 값을 미리 설정해야 사용할 수 있으며, this.setState() 메소드로만 값을 업데이트 해야 합니다. 
 
 그니까 자식컴포넌트 딴에서 값 업데이트가 가능하다. 단 this.setState()메소드 안에서만 업데이트 가능!

#순서
1. state 초깃값 설정하기
2. state 랜더링 하기
3. state 값 업데이트 하기


```javascript
Mycomponent.js중 render함수
render(){
    return (
        <div>
            <p> 숫자: {this.state.number}</p>
            <button onClick={()=>{
                this.setState({
                    number: this.state.number +1
                })
            }}> 더하기</button>
        <div>
    )
}

state = {
    number : 0
}
```

# 이밴트 핸들링
이벤트에 실행할 자바스크립트 코드를 전달하는 것이 아니라, 함수형태의 값을 전달 합니다. 

그렇기 때문에 onClick 이나 onChange와 같은 이벤트핸들러에 전달할 함수를 따로 빼내서 컴포넌트 임의 메서드를 만들 수 있다.

기존 react에서는 이벤트 핸들러에 전달할 함수를 만들기 위해 bind를 사용했지만 우리는 바벨의 transform-class-properties문법을 사용하여 간단하게 표현할 수 있다. 

```javascript
import React, {Component} from 'react';

class EventPractice extends Conponent{
        
    state = {
        message:''
    }

    handleChange = (e)=>{
        this.setState({
            [e.target.name]:e.target.value
        });
    }

    handleClick = ()=>{
        alert(this.state.message);
        this.setState({
            [e.target.name]: ''
        });
    }

    handleKeyPress = (e)=>{
        if(e.key === 'Enter'){
            this.handleClick();
        }
    }


    render(){
        return(
            <div>
            <input 
                type='text'
                name='message'
                placeholder='아무거나 입력해보세요'
                value='this.state.message'
                onChange={this.handleChange}
                onKeyPress={this.handleKeyPress}
            />
            <button onClick={this.handleClick}>확인</button>
            </div>
        )
    }
}

export default EventPractice
```
## ref: DOM에 이름달기
 일반적으로 DOM요소에 이름을 달 때 id를 사용하는데 html에서 id를 사용하여 DOM에 이름을 다는 것 처럼 리액트 프로젝트 내부에서 DOM에 이름을 다는 법이 있습니다. 그것이 ref입니다.

### 순서
 1. ValidationSample 컴포넌트 만들기
 2. input에 ref 달기
 3. 버튼 누를 때 마다 input에 포커스 주기

ref를 달아야 하는 DOM에 ref속성을 추가할 때는 props를 설정하듯이 하면 됩니다. ref값으로는 콜백함수에 전달합니다.

```javascript

<input ref={(ref)=>{this.input = ref}}></input>

<MyComponent
    ref={(ref)=>{this.myComponent=ref}}
    />
```
이렇게 하면 MyComponent 내부의 메서드 및 멤버변수에도 접근할 수 있습니다.

### 부모 컴포넌트에서 스크롤바 내리기
1. ScrollBox 컴포넌트 만들기
2. 컴포넌트에 ref달기
3. ref를 이용하여 컴포넌트 내부 메서드 호출하기

```javascript
App.js

import React, {Component} from 'react'
import ScrollBox from '

```
```javascript
ScrolBox.js

import React, {Component} from 'react';

class ScrollBOx extends Component{

    scrollToBottom= ()=>{
        const {}
    }
}


```

## 컴포넌트의 반복
자바스크립트 배열 객체의 내장함수인 map 함수를 사용하여 반복되는 컴포넌트를 랜더링 할 수 있다. 
map 함수는 파라미터로 전달된 함수를 사용하여 배열 내 각 요소를 프로세싱 한 후 그 결과로 새로운 배열을 생성합니다. 

### 유동적인 데이터 렌더링
1. 초기 state 설정하기
2. 데이터 추가기능 구현하기
3. 데이터 제거 기능 구현하기

```javascript 

import React, {Component} from 'react';

class IterationSample extends Component{

    //1. 초기 데이터 설정하기.
    state = {
        names :['눈사람','얼음','눈','바람'],
        name : ''
    };

    //2. 데이터 추가 기능 구현
    handleChange = (e)=>{
        this.setState({
            name: e.target.value
        });
    }

    handleInsert = ()=>{
        // name 배열에 값을 추가하고, name값을 초기화 합니다
        this.setState({
            names:this.state.names.concat(this.state.name),
            name:''
        });
    }

    handleRemove = (index)=>{
        // 편의상 name의 레퍼런스를 미리 만듭니다.
        const {names} = this.state;

        /* 배열을 자르는 내장 함수 slice와
            전개 연산자 ...을 사용하여 index번째 값을 제외한 값들을
            배열에 넣어줍니다.
        */
        this.setState({
            names: [
                ...names.slice(0,index),
                ...names.slice(index+1,names.length)
            ]
        });
    }

    handleKeyPress = (e) =>{
       if (e.key === 'Enter') {
           this.handleInsert();
       }
    }

    render(){
        const nameList = this.state.names.map(
            (names, index) => (
            <li 
                key={index}
                onDoubleClick={() => this.handleRemove(index)}>
                {names}
            </li>)

        );
        return (
            <div>
                <input
                    type='text'
                    onChange={this.handleChange}
                    onKeyPress={this.handleKeyPress}
                    value={this.state.name}/>
                <button onClick={this.handleInsert}>추가</button>

                <ul>
                {nameList}
                </ul>
            </div>
        );
    };

}

export default IterationSample;
```


### 주의사항
key 값은 절대로 중복되면 안됨.
key 값이 중복된다면 렌더링 과정에서 오류가 발생하한다. 그리고 state안에서 배열을 변경할 때 기존의 배열을 직접 접근하여 수정하는 것이 아니라 새로운 배열을 만들고 setState 메서드로 적용해야 한다.


## 컴포넌트와 라이프사이클의 메서드

라이프 사이클은 총 세가지 마운트 업데이트 언마운트 카테고리로 나누어진다.

### 마운트
DOM이 생성되고 웹브라우저 상에 나타나는 것을 마운트라고 한다. 이때 호출되는 메서드는
1. constructor : 컴포넌트를 새로 만들 때마다 호출되는 클래스 생성자 메서드
2. getDerivedStateFromProps : props에 있는 값을 state에 동기화하는 메서드
3. render : 우리가 준비한 UI를 랜더링하는 매서드
4. componentDidMount: 컴포넌트가 웹 브라우저상에 나타난 후 호출하는 메서드

### 업데이트
컴포넌트가 업데이트할때는 다음 총 네 가지 경우입니다.
1. props가 바뀔때
2. state가 바뀔때
3. 부모 컴포넌트가 리렌더링될 때
4. this.forceUpdate로 강제로 렌더링을 트리거할 때
 
 이때 호출되는 메서드는
 1. getDerivedStateFromProps : 마운트 과정에서도 호출하며, props가 바뀌어서 업데이트 할때도 호출한다.
 2. shouldComponentUpdate : 컴포넌트가 리렌더링을 해야 할지 말아야할지를 결정하는 메서드로 false를 반환하면 아래 매서드를 호출하지 않습니다.
 3. render : 컴포넌트를 리랜더링합니다.
 4. getSnapshotBeforeUpdate : 컴포넌트 변화를 DOM에 반영하기 바로 직전에 호출하는 메서드 입니다.
 5. componentDidUpdate: 컴포넌트의 업데이트작업이 끝난 후 호출하는 메서드 입니다

 ### 언마운트
 컴포넌트를 DOM에서 제거하는 것을 언마운트라고 합니다.
 1. componentWillUnmount : 컴포넌트가 웹 브라우저상에서 사라지기 전에 호출하는 메서드 입니다.


 #### render()함수
 이 메서드는 컴포넌트 모양새를 정의한다.
 이 매서드 안에서 this.props와 this.state에 접근 할 수 있으며 리액트 요소를 반환 합니다. 요소는 div같은 태그가 될 수 도 있고, 따로 선언한 컴포넌트가 될 수도 있습니다. 아무것도 보여주고싶지 않다면 null 값이나 false값을 반환한다.

주의: 이 메서드 안에서 절대로 state를 변형해서는 안되며 웹드라우저에 접근해서도 안된다. DOM정보를 가져오거나 변화를 줄 때는 componentDidMount에서 처리해야한다. 

#### constructor 메서드
컴포넌트의 생성자 메서드로 컴포넌트를 만들 때 처음으로 실행 이 메서드에서 초기 state를 정할 수 있다.

#### getDerivedStateFromProps 메서드
props로 받아 온 값을 state에 동기화 시키는 용도로 사용하며 컴포넌트를 마운트 하거나 props를 변경할 때 호출합니다. 

#### componentDidMount 메서드
컴포넌트를 만들고 첫 렌더링을 다 마친 후에 실행됩니다. 이 안에서 다른 자바스크립트 라이브러리 또는 프레임워크 함수를 호출하거나 이벤트 등록,setTimeout, setInterval, 네트워크 요청 같은 비동기 작업을 처리하면 된다. 

#### shouldComponentUpdate 메서드
props 혹은 state를 변경했을 때 리렌더링을 시작할지 여부를 지정하는 메서드로 이 안에서 현재 props와 state를 this.props this.state로 접근하고 새로 설정될 props또는 state는 nextProps와 nextState로 접근할 수 있습니다.

#### getSnapshotBeforeUpdate 메서드
이 메서드는 render메서드를 호출한 후 DOM에 변화를 반영하기 바로 직전에 호출하는 메서드. 여기서 반환하는 값은 componentDidUpdate에서 세번째 파라미터인 snapshop값으로 전달받을 수 있는데 주로 업데이트하기 직전의 값을 참고할 일이 있을 때 활용된다. 

#### componentDidUpdate 메서드
리랜더링이 완료한 후 실행되는 메서드로 업데이트가 끝난 직후이므로 DOM관련 처리를 해도 무방. 여기에서 prevProps또는 prevState를 사용하여 컴포넌트가 이전에 가졌던 데이터에 접근할 수 있습니다. 또 getSnapshotBeforeUpdate에서 반환한 값이 있다면 여기에서 snapshot 값을 전달받을 수 있습니다.

#### componentWillUnmount 메서드
이것은 컴포넌트를 DOM에서 제거할 때 실행합니다. componentDidMount에서 등록한 이벤트, 타이머, 직접생성한 DOM이 있다면 여기에서 제거 작업을 해야 합니다. 

### 정리
라이프사이클 메서드는 컴포넌트 상태에 변화가 있을 때마다 실해하는 메서드이고 이 메서드들은 서브파티 라이브러리를 사용하거나 DOM을 직접 건드려야 하는 상황에서 유용합니다. 추가로 컴포넌트 업데이트의 성능을 개선할 때는 shouldComponentupdate가 중요하게 사용된다. 


## 리액트 컴포넌트 스타일링
리액트에서 컴포넌트를 스타일링하는데 획일화된 방식 x

