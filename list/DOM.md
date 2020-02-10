# DOM(Document Object Model)

javascript로 HTML의 제어를 통해서 웹 사이트를 인터랙티브하게 변경할 수 있다.  
HTML을 제어하기 위해서는 DOM API를 사용할 수 있다.  
_+_ 이벤트 프로그래밍도 이해해야함.

## DOM 제어
- node를 탐색할 줄 알아야 한다. 
- node를 찾을 수 있다.
- node의 구조를 변경(추가, 삭제 등)할 수 있다.  


브라우저에서는 HTML 코드를 DOM(Document Object Model)이라는 객체 형태의 모델로 저장합니다.   
그렇게 저잘된 정보를 DOM Tree라고 한다. HTML element는 Tree 형태로 저장된다.  


<img alt="DOM" width="500"  src="https://t1.daumcdn.net/cfile/tistory/993490335A0551C202">  

<img alt="DOM Tree, CSSOM, Render Tree" width="500" src="https://t1.daumcdn.net/cfile/tistory/99271F335A0551690B">   


## node 탐색 API  
- **css Selector**는 `querySelector`와 `querySelectorAll`을 사용하면 된다.  
- **getElementById()**: id 정보를 통해 selector를 찾을 수 있다.   
- **Element.querySeletor**: DOM을 찾는 데 유용하다. 

## node 탐색 방법
node는 여러가지 DOM 타입들이 상속하는 인터페이스이며 그 다양한 타입들을 비슷하게 처리할 수 있게 한다.  

다음의 인터페이스들은 모두 `node`로부터 메소드와 프로퍼티를 상속한다. `Document`, `Element`, `CharaterData(text, comment)`, `DocumentFragment`, `DocumentType`  
이 인터페이스들은 메소드나 프로퍼티가 적합하지 않은 경우에 null을 반환할 수 있다.  
 
### 프로퍼티

> **[`Node.childNodes`](https://developer.mozilla.org/ko/docs/Web/API/Node/childNodes)`읽기전용 📖`**: 주어진 요소의 자식 노드 모음(collection)을 반환합니다.  
>
> **[`Node.firstChild`](https://developer.mozilla.org/ko/docs/Web/API/Node/firstChild)`읽기전용 📖`**: 트리에서 노드의 첫 번째 자식이나 null(노드가 자식이 없으면)을 반환합니다.  
>
> **[`Node.lastChild`](https://developer.mozilla.org/ko/docs/Web/API/Node/lastChild)`읽기전용 📖`**: 노드의 마지막 자식을 반환합니다.  
>
> **[`Node.nextSibling`](https://developer.mozilla.org/ko/docs/Web/API/Node/nextSibling)`읽기전용 📖`**: 부모의 childNodes 목록에서 지정된 노드 바로 다음에 있는 노드를 반환하거나 지정된 노드가 해당 목록의 마지막 노드이면 null 값을 반환합니다.  
>
> **[`Node.nextSibling`](https://developer.mozilla.org/ko/docs/Web/API/Node/nodeType)`읽기전용 📖`**: 노드의 타입을 나타냅니다.  
>
>|**Constant**|**Value**|**Description**|
>|:--|:--:|:--|
>|Node.ELEMENT_NODE|1|Elemnet 노드 등 `<p>` 또는 `<div>` |
>|Node.TEXT_NODE|3|실제 `Text`의 `Element`|
>|...||이외에도 여러가지가 있으나 잘 사용하지 않습니다. |
>
>
>**[`Node.ownerDocument`](https://developer.mozilla.org/ko/docs/Web/API/Node/ownerDocument)`읽기전용 📖`**: 이 속성에 의해 반환된 document는 실제 HTML 문서의 모든 child 노드들이 생성되는 메인 객체입니다. 이 속성이 document 그자체 노드에서 사용될 경우, 결과는 null이 됩니다.  
>
>**[`Node.previousSibling`](https://developer.mozilla.org/ko/docs/Web/API/Node/previousSibling)`읽기전용 📖`**: 현재 호출하는 노드가 속해 있는 부모의 childNodes 목록에서 특정 자식 노드를 리턴하거나 chideNodes 목록의 첫번째 노드일 경우 null 값을 리턴합니다.  
>
>**[`Node.textContent`](https://developer.mozilla.org/ko/docs/Web/API/Node/textContent)`읽기전용 📖`**: 노드와 그 자손의 텍스트 내용을 표시한다.
>

### 메소드

> **[`Node.appendChild()`](https://developer.mozilla.org/ko/docs/Web/API/Node/appendChild)**: 한 노드를 특정 부모 노드의 자식 노드 리스트 중 마지막 자식으로 붙입니다.  
>
> **[`Node.cloneNode()`](https://developer.mozilla.org/ko/docs/Web/API/Node/cloneNode)**: 호출한 Node의 복제된 Node를 반환합니다.  
> 
> **[`Node.compareDocumentPosition()`](https://developer.mozilla.org/ko/docs/Web/API/Node/compareDocumentPosition)**  
>
> **[`Node.contains()`](https://developer.mozilla.org/ko/docs/Web/API/Node/contains)**: 주어진 인자가 Node의 자손인지 아닌지에 대한 Boolean 값을 리턴합니다.  
> 
> **[`Node.hasChildNodes()`](https://developer.mozilla.org/ko/docs/Web/API/Node/hasChildNodes)**: 현재 Node에게 자식 노드(child nodes)가 있는지를 Boolean값으로 반환합니다.  
> 
> **[`Node.insertBefore()`](https://developer.mozilla.org/ko/docs/Web/API/Node/insertBefore)**: 참조된 노드 앞에 특정 부모의 노드의 자식 노드를 삽입합니다. 만약 주어진 자식 노드가 document에 존재하는 노드를 참조한다면 insertBefore()가 자식 노드를 현재 위치에서 새로운 위치로 옮깁니다.  
> 
> https://developer.mozilla.org/ko/docs/Web/API/Node


## node 생성과 추가
document. 으로 사용할 수 있는 APIs: https://www.w3schools.com/jsref/dom_obj_document.asp  

element. 으로 사용할 수 있는 APIs: https://www.w3schools.com/jsref/dom_obj_all.asp  