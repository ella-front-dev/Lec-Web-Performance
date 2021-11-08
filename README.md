# Lec-Web-Performance

## Project 설치 및 실행

```bash
# 설치
npm install

# 개발 서버 실행
npm start

# backend 서버 실행
npm run server

```

## Lecture 2 : 통계 사이트 최적화

### 애니메이션 분석 및 최적화
- 애니메이션이 원리
- 쟁크 현상 : 애니메이션이 버벅이는 현상

- 브라우저 동작
  - Reflow : layout, paint 과정 모두 실행 / display, position, width, height, float, font-size, font-weight ...
  - Repaint : layout 제외하고 paint과정만 실행 /  background, color, border ...
  - GPU가 관여할 수 있는 속성 : layout, paint 모두 제외 / transform, opacity

### Component lazy loading /module
- webpack-bundle-analyzer(cra-bundle-analyzer)를 사용해서 분석
- 모달 컴포넌트를 분리해서 필요할 때 가져오도록 적용

### Component Preloading
- 이슈 : lazy loading 때문에 모달을 띄울때 Delay 현상이 나타남
- 해결 : 모달 코드를 preload를 통해서 미리 준비한다.
- 타이밍
  - 버튼위에 마우스를 올려놨을때 preload 실행
  - 모든 컴포넌트 마운트가 끝났을때 preload 실행

### Image Preloading
- javascript image 속성을 이용해서 preload 생성
- 단, 같은 이미지주소를 계속 요청해도 이미지를 새로 가져온다.
- 마운트가 끝났을때 preload 실행되어 이미지를 preload하고 이후 모달이 띄어졌을때는 캐시로 해당 이미지를 가져온다.



