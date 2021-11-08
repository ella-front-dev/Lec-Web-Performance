# Lec-Web-Performance

## Lecture 1 : 블로그 사이트 최적화

### 사이트 검사
Chrome LightHouse를 이용해서 검사

[ 검사 결과 ]
- 이미지 최적화 필요
- JS 파일 최적화 필요

### 이미지 최적화
- image CDN을 이용한 최적화
  imgIX[https://imgix.com/]

- 
  
### Bottleneck
- 로딩이 지연되는 특정 함수 분석
  원인 : removeSpecialCharacter 함수로 인해 로딩 지연

- 로딩 지연 함수 분석 및 해결
  - 특수문자를 제거를 위해 이중 루프를 replace와 정규식을 이용하는 방식으로 수정
  - 페이지에 표시되지 않는 문자들은 제거  

### bundle 파일
- 파일 분석툴
  - bundle 파일 분석을 위해서 "webpack-bundle-analyzer"[https://www.npmjs.com/package/webpack-bundle-analyzer] 를 이용

  - webpack에 바로 적용하는데 어려움이 있는 creat-react-app에서는 "cra-bundle-analyzer"[https://www.npmjs.com/package/cra-bundle-analyzer]를 사용

- 파일 분석
  - refractor 영역이 많이 차지함
  - package-lock.json에서 react-syntax-highlighter 안에 refractor를 찾음 (마크다운에서 코드블록 스타일링에 쓰는 패키지)
  - 해당 패키지를 view페이지에서만 사용되도록 수정하면 로딩 시간 단축 가능

- Code Splitting : 코드 분할
  - 분할 패턴 : 페이지별로 , 모듈별로 등등
  - 각각의 페이지의 bundle 파일을 만들어서 그 페이지가 로딩될때 해당 파일을 가져와서 사용
  - code splitting을 적용하기 위해서는 webpack에서 따로 설정이 필요( webpack code splitting[https://webpack.js.org/guides/code-splitting/])
  - Route-based code splitting 적용
    
### 텍스트 압축
- 종류
  - GZip
  - Deflate
- 운영모드에서 확인
- serve.js를 통해서 텍스트 압축 적용 여부 선택



