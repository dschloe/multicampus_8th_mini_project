# 커밋 메시지의 기본 구조
- 가장 널리 쓰이는 3단 구성 방식입니다.
    + Subject (제목): 변경 사항을 한 줄로 요약 (50자 이내).
    + Body (본문): '무엇을', '왜' 변경했는지 상세히 설명 (한 줄당 72자 이내).
    + Footer (바닥글): 이슈 트래커 ID(예: #12) 등을 참조할 때 사용.
```
type: Subject (제목)

Body (본문 - 선택 사항)

Footer (바닥글 - 선택 사항)
```

# 자주 사용하는 커밋 타입 (Prefix)
- 포트폴리오용 프로젝트라면 아래와 같은 표준 타입을 사용하는 것이 좋습니다.

| 타입 (Type) | 의미 | 사용 예시 |
| :--- | :--- | :--- |
| **Feat** | 새로운 기능 추가 | `feat: 당뇨병 예측을 위한 XGBoost 모델 추가` |
| **Fix** | 버그 수정 | `fix: 결측치 처리 로직 오류 수정` |
| **Docs** | 문서 수정 (README 등) | `docs: 데이터 사전 테이블 업데이트` |
| **Style** | 코드 포맷 변경 (세미콜론, 들여쓰기 등) | `style: 주피터 노트북 셀 구조 정리` |
| **Refactor** | 코드 리팩토링 (기능 변화 없음) | `refactor: 전처리 로직 함수화` |
| **Chore** | 빌드 업무, 패키지 매니저 설정 등 | `chore: requirements.txt 라이브러리 추가` |

# 터미널 활용 팁
```
# 한 줄로 커밋할 때
git commit -m "feat: 당뇨병 예측 모델 성능 개선"

# 제목과 본문을 나누어 커밋할 때
git commit -m "feat: 당뇨병 예측 모델 성능 개선" -m "- XGBoost 하이퍼파라미터 튜닝 적용" -m "- Recall 점수 0.82 달성"

git commit -m "feat: 당뇨병 예측을 위한 XGBoost 모델 추가" -m "- Recall 성능 향상을 위해 Scale_pos_weight 조정" -m "- 최종 AUC-ROC: 0.89 달성"
```

# 커밋 이력 확인하기
```
git log --oneline --graph --all
```