*CSS 선택자*

1.input type selector

        <style>
        input[type=text] {
          background:blue;
        }
        input[type=password] {
          background:yellow;
        }
        input[type=reset] {
          background:green;
        }
        input[type=button] {
          background:red;
        }
        </style> 
        
2.문자열 속성 선택자     

    <style>
      img[src~='a1.jpg'] { /* 속성값 자체 비교 */
        border:10px solid red;
      }  /* img태그의 src 속성값이 'a1.jpg' 인 것 */

      img[src|='b1.jpg'] {  /* 속성값 자체 비교 */
        border:10px solid blue;
      } /* img태그의 src 속성값이 'b1.jpg' 인 것 */

      /*1번과 2번의 차이는 뭘까*/

      img[src$=gif] {  /* 끝나는 값 */
        border:10px solid green;
      } /* img태그의 src 속성값이 gif로 끝나는 것 */

      img[alt^='f'] {  /* 시작하는 값 */
        border-right:10px solid yellow;
      } /* img태그의 alt 속성값이 f로 시작하는 값 */

      img[src*='4'] {  /* 일부값이 포함되어 있는것 */
        border-left:10px solid black;
      } /* img태그의 src 속성값 내에 4라는 값이 있는 것 */
    </style>
    
3.ID,CLASS선택자

    <style>
      li[id=aa] { /* li태그중에 id속성이 'aa'인 것 */
        color:red;
      }
      li[class=aa] {
        color:blue;
      }
    </style>
    
    
4.제한 선택자 

    <style> /* 브라우저에서 스타일의 적용순서는 라인순서대로 실행 */

      header b { /* header 태그내의 모든 b태그에 적용 */
        color:blue;
      }

      header > b { /* header 태그 바로밑 b태그에 적용 */
        font-size:50px;
        color:green;
      }

      header ul li { /* header 태그 밑의 모든 후손 ul 밑의 모든 후손 li 에 적용*/
        font-size:30px;   /* 문서내의 모든 li태그라는 뜻 */
      }

      header > ul > li { /* header 태그밑 자손 ul 밑의 자손 li에 적용 */
        border:1px solid red;
      }

      header > ul > li b {  /* header 자손ul 자손li 후손b  */
        text-decoration:underline;
          background:yellow;
      }

      header > ul > li > ul > li > b { /* 무조건 자손 */
        background:yellow;
      }
    </style>
    
    
5. 동위선택자
    
        <style>
            h1 + h2 {  /* h1태그 바로 다음에 오는 h2 태그에 적용 */
              color:red; /* 1번바로 뒤 2번, 7번바로뒤 8번 해당 */
            }
            h1 ~ h2 { /* h1 태그 뒤에 있는 모든 h1태그 */
              background:yellow; /* 1번뒤에 오는 2,8,9번 해당 */
            }

            h2 + div { /* h2 태그 바로 뒤에 오는 div태그에 적용 */
              text-decoration:underline; /* 2번바로 뒤 3번, 9번 바로뒤 10번 */
            }
            h2 ~ div {
              font-size:50px;  /* 2번 뒤에 오는 3,5,7,10,11 */
            }
          </style>
          
          
          
6.반응형 선택자          

      <style>
      /* link와 visited를 링크선택자로 부르기도 함 */
      a { /* 모든 a 태그에 적용 */
        font-size:40px;
      }

      a:link {  /* a태그가 링크된것은 적용 href속성이 없으면 적용안됨*/
        font-family:궁서체;
      }

      a:visited { /* 현재 브라우저가 방문한 사이트 */
        color:green;
      }

      a:hover {  /* 링크영역에 마우스가 올라오면 */
        text-decoration:underline;
        color:red;
      } 

      a:active { /* 링크영역에 마우스가 클릭되고 있을때 */
        color:yellow;
      }

      #menu:hover { /* hover는 텍스트 롤오버기능으로 많이 사용함) */
        color:white;
        background:blue;
      }
    </style>
    
    
    
7.상태선택자


    <style>
      input:checked { /* 체크가 되면 속성이 적용 radio,checkbox에서 주로사용 */
        width:30px;
        height:30px;
      }
      input:disabled { /* 비활성화된 폼태그 */
        background:red;
      }
      input:enabled { /* 활성화된 폼태그(브라우저에따라 조금 틀림:radio) */
        background:blue;
      }
      input:focus { /* 포커스가 된 폼태그 */
        color:white;
      }

    </style>
    
    
    
8.구조 선택자


    <style>
      /* n값은 0부터 시작하는것으로 하면 됨 */
      /* li태그의 순서는 1부터 계산함 */

      li:first-child { /* li 태그중에 첫번째 */
       background:blue;
      }
      li:last-child { /* li 태그중에 마지막 */
       background:red;
      }
      li:nth-child(2n) { /* li태그 앞에서 부터 2n=> 2,4,6,8,10 */
       font-size:20px;
      }
      li:nth-last-child(2n) { /* li태그 뒤에서 부터 2n=> 2,4,6,8,10 */
       color:green;
      }
      li:nth-child(3n) {  /* li태그 앞에서 부터 2n=> 3,6,9 */
       text-decoration:underline;
      }
      li:nth-child(4n+1) { /* li태그 앞에서 부터 4n+1=> 1,5,9 */
       font-family:궁서체;
      }
    </style>
    
    
    
9.가상선택자    


    <style>
      li::after {     /* li태그뒤에 content의 내용을 추가 */
        content:"!!!!";
        color:red;  /* content의 스타일 지정 */
        text-decoration:underline;
      }
      li::before {   /* li태그앞에 content의 내용을 추가 */
        content:"좋아요";
        color:red;
        font-size:20px;
      }
    </style>
    
    
    
    
10.문자 선택자


    <style>
      li::first-letter { /* li태그의 첫번째 글자 */
        font-size:20px;
        color:blue;
      }
      li::first-line {  /* li태그의 첫번째 라인 */
        background:yellow;
      }

    </style>


11.반응 문자 선택자

    <style>
      p::selection { /* p태그내에 드래그하여 선택하게 되면 적용 */
        color:red;
      }
      ::selection { /* 전체 문서에서 드래그하여 선택하게 되면 적용 */
        background:yellow;
      }
    </style>
    
    
    
12.부정선택자

    <style>
      li:not(.aa) { /* class=aa가 아닌것에 적용 */
        color:blue;
        font-size:20px;
      }
      input:not([type=text]) { /* input태그에서 type속성이 text가 아닌것에 적용 */
        background:red;
      }
      :not(.aa) {  /* 전체문서 적용이 안됨 */
        font-size:40px;
      }
    </style>
