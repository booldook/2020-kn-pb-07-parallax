# HTML 정리
### block: 부모의 크기에 꽉 차게 영역을 차지한다(layout 잡을 때, 내용을 감쌀 때)
1. **div**: 특징이 없다. 
2. **h1~h6**: 제목을 나타낼 때 쓴다. (font-weight: bold, padding, margin을 가진다)
3. **p**: 내용을 나타낼 때 쓴다. (margin-bottom을 가진다)
4. **ul, li, dl, dd, dt**: 목록을 나타낼 때 쓴다.
5. **form**
6. **table**: 목록을 표로 나타낼 때 쓴다.

```html
<table>
	<thead>
		<tr>
			<th>제목</th>
			<th>제목</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>내용</td>
			<td>내용</td>
		</tr>
	</tbody>
</table>
```

```css
/* table Normalize */
table, thead, tbody, tr, th, td {margin: 0; padding: 0; box-sizing: border-box;}
table {border-collapse: collapse;}
```

7. **Normalize**: block요소는 속성을 가지고 있기 때문에 초기화 하여 필요할 때 속성을 부여해서 쓴다

```css
html, body, h1, h2, h3, h4, h5, h6, p, div, form, input, textarea, select, header, section, article, aside, footer, table, thead, tbody, tr, td, th, ul, ol, li, dl, dt, dd {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-weight: normal;
}
```
### inline: 글자요소(한줄에 나타남, 내용자체)
1. **span**: 글 안에서 영역을 설정할 때
2. **a**: 링크[href="#" target="_self(기본), _blank(새창), myName(프레임이름)"]
3. **i**: 이탤릭을 표시 - css의 font-style: italic;과 같다.
4. **b, strong**: 볼드를 표시 - css의 font-weight: bold;와 같다.
5. **img**: 이미지를 나타낸다[src="../img/p.jpg"], 이미지도 영문글자와 같이 취급되어 기준선이 baseline으로 잡혀서 하단으로 기준선을 아래와 같이 변경하여야 한다.
6. input, select, textarea 등등의 form요소
7. inline과 inline-block의 차이점은 width, height의 유, 무 차이.
- inline: span, i, b, strong
- inline-block: img, input, select, textarea

```css
/* img Normalize */
img {
	vertical-align: bottom;
}
```


# CSS 정리
## 기본속성
1. initial: 기본값으로 재지정하겠다.
2. unset: 상속받은값을 삭제하겠다.
3. inherit: 부모의 값을 상속받겠다.
```html
<div class="box">
	<p class="list">가나다</p>
</div>
```
```css
.box {color: red;}
.list {color: inherit;}
```

## text 관련
1. font-family: 'Loto', sans-serif;
2. font-size: 16px(기본)
3. color: red, #f00, rgb(255, 0, 0), rgba(255, 0, 0, 1), hsl ...
4. font-weight: normal, lighter, bold, bolder, 200, 300, 400 ...
5. font-style: italic, oblique;
6. text-align: center, left, right, justify
7. vertical-align: top, middle, baseline(기본값), bottom
8. text-decoration: line-through, underline, overline, none
9. letter-spacing: 자간
10. line-height: 줄간 

## layout 관련
1. float: left, right, none
2. position: static(기본값), relative(기준점), absolute, fixed(화면을 기준점)
3. flex
4. grid

## Dimension 관련
1. width, height - 고정값
2. max-width, max-height - 최대값
3. min-wdith, min-height - 최소값
4. margin, padding ...


## Design 관련
1. border: 1px solid(dashed, dotted, double, inset, outset, groove, none) red
2. background-image: url('../img/bg.gif');
3. background-repeat: (repeat) | no-repeat | repeat-x | repeat-y
4. background-position: (left top) | center | [left, center, right] [top center bottom]
5. background-position: 200px 100px | 30% 50% ...
6. background-size: (자기사이즈) 100% auto | auto 100% | cover
7. background-size: 200px 500px
8. background-attachment: fixed <-- parallax효과
9. background-image: linear-gradient([각도], #9deb7f, #256225 ...);
	- [각도]: to left | to left top | 45deg
10. background-image: radial-gradient(#9deb7f, #256225 ...);
11. 합쳐쓰기 -> background: 컬러 url() repeat position;

## 기타
### pseudo-element(:, ::)
1. .clear::after -> 태그가 닫히기 직전
2. .box::before -> 태그가 열리지마자

```html
<div>
	<!-- :before -->
	<p>ABCD</p>
	<!-- :after -->
</div>
```
3. :hover, :link, :active, :visited -> 순서는 아래처럼
- link: 기본값(한번도 방문하지 않았던 사이트)
- visited: 방문했던 사이트 링크
- hover: 마우스를 올리면...
- active: 마우스를 누르고 있는 동안

## 선택자(Selector)
1. 아이디선택자: #box
2. 클래스선택자: .box
3. 태그선택자: div
4. 자식선택자: div > p (바로 밑에있는 자식)
5. 자손선택자: div p (안에 있는 자손)
7. 순서선택자: :first-child, :last-child, :nth-child(2)
8. 읽기-붙여쓰면 그리고로 읽는다.
- .wrapper > span:last-child -> span이면서 마지막자식
- .list.active -> 클래스list이면서 클래스active 인 요소
9. 속성선택자: input[name="userid"], button[disabled="disabled"]
10. :not(:last-child) - 제외
11. 그 외의 선택자는 [여기](https://www.w3schools.com/cssref/css_selectors.asp)를 참고한다.
