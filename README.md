# 백운교회 GitHub Pages 홈페이지

이 폴더는 별도 서버나 데이터베이스 없이 GitHub Pages에서 바로 실행되는 정적 홈페이지입니다.

## 파일 구성

- `index.html` : 홈페이지 본문
- `style.css` : 전체 디자인과 모바일 반응형 스타일
- `.nojekyll` : GitHub Pages가 파일을 그대로 배포하도록 하는 설정
- `assets/` : 교회 사진을 보관할 폴더

## GitHub Pages에 올리는 방법

1. GitHub에서 새 저장소(repository)를 만듭니다.
2. 이 폴더 안의 파일을 저장소 최상위에 그대로 업로드합니다.
3. 저장소의 **Settings → Pages**로 들어갑니다.
4. **Build and deployment → Deploy from a branch**를 선택합니다.
5. Branch를 `main`, Folder를 `/ (root)`로 선택하고 Save 합니다.
6. 잠시 후 GitHub가 공개 홈페이지 주소를 만들어 줍니다.

## 유튜브 주소 바꾸기

`index.html`에서 아래 문구를 검색합니다.

```html
https://www.youtube.com/results?search_query=백운교회+신상균
```

이 주소를 실제 백운교회 유튜브 채널 주소 또는 영상 목록 주소로 바꾸면 **말씀 보러가기** 버튼이 그곳으로 연결됩니다.

## 교회 사진 넣기

사진 파일을 `assets/` 폴더에 올립니다. 예: `church-front.jpg`, `worship-01.jpg`.

현재 홈페이지의 앨범 부분은 사진이 없어도 디자인이 깨지지 않는 자리표시자로 만들어 두었습니다. 실제 사진으로 바꾸려면 `index.html`의 `gallery-placeholder` 부분을 다음처럼 바꿉니다.

```html
<figure class="gallery-placeholder">
  <img src="assets/worship-01.jpg" alt="백운교회 주일예배 모습">
  <figcaption>주일예배와 절기예배</figcaption>
</figure>
```

그리고 `style.css`에 다음을 추가하면 사진 크기가 자동으로 맞습니다.

```css
.gallery-placeholder img {
  width: 100%;
  aspect-ratio: 4 / 3;
  object-fit: cover;
}
```

## 장로 명단 수정

현재 인원은 원로장로 4명, 시무장로 2명, 은퇴장로 1명, 명예장로 1명으로 표시되어 있습니다. 이름과 사진을 넣으려면 `index.html`의 `id="leaders"` 부분을 수정합니다.

## 예배시간 수정

`index.html`에서 `id="worship"`를 검색하면 예배시간을 바로 수정할 수 있습니다.

## 중요한 점

GitHub Pages는 정적 홈페이지이므로 홈페이지 화면에서 관리자 로그인 후 사진을 직접 업로드하는 기능은 기본적으로 없습니다. 사진과 글을 수정할 때는 GitHub 저장소의 파일을 교체하거나 수정하면 됩니다.
