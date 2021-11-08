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



