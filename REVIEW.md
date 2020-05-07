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

# 기타