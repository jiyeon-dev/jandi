# Jandi

# tsconfig.json 옵션

### incremental 과 composite

- composite: true인 경우
  - 자동으로 증분 빌드 기능이 포함됨
  - .tsbuildinfo 파일도 자동 생성
  - 더 엄격한 제약사항이 추가됨
- 선택 기준
  - 단순히 빌드 성능 최적화만 필요 → incremental 사용
  - 프로젝트를 모듈식으로 나누고 싶음 → composite 사용
- 현재 프로젝트의 경우
  - Vite 기반의 단일 프로젝트
  - 다른 TypeScript 프로젝트와의 참조 관계가 없음
  - 따라서 incremental만으로 충분함
- 메모리를 조금 더 사용하지만, 변경되지 않은 파일들은 빌드 결과를 재사용하기 때문에 빌드 속도가 빠르다.
  - 가끔 캐시가 잘못된 경우 `tsc --build --clean` 으로 초기화 필요할 수 있음.
