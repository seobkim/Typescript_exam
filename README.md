```typescript
/*보통 명시적 표현은 최소한으로 사용하는게 좋음 가능한 Typescript가 추론하는 것이 좋음*/
----------------------------------------------------------------------
let num : number = 1;
let str : String = 'hello';
let bool : boolean = false;
let stirngArr : String[]= ['h','i'];


let obj : {
    // ?: optional parameter : 옵션을 주지않으면 객체 값 할당 시 키값에 값 모두 할당해야함
    name? : String, 
    age? : number
}

obj = {
    name : 'jack',
    // age:11
    }

// obj => age 는 undefined 일 수 있기때문에 typeScript 가 오류 발생시킴
// if(obj.age < 10){
//     console.log(obj.age);
// }
// O
if(obj.age && obj.age < 10){
    console.log(obj.age);
}



// 같은 key를 가진 여러 객체를 생성시 alias타입을 지정하여 type 선언가능
type Age = number;
type  PersonInfo = {
    name? : String,
    age? : Age,
}

const obj1 : PersonInfo={
    name : 'person1',
    age : 11
}

const obj2 : PersonInfo={
    name : 'person2',
    age : 12
}

//리턴타입 Alias 로 지정
const  testMethod = (name:String) : PersonInfo => ({name});

let testReturn = testMethod('kim');
testReturn.age = 11;


// readonly 속성 추가 가능
type  PersonInfo_2 = {
    readonly name? : String,
    age? : Age,
}

const number2 : readonly number[] = [1,2,3,4];
// number2.push(5) => error
```
