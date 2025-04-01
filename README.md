# 👚 Super Duper
소개 사이트: [https://www.skttechacademy.com/nonmember/flyAi/flyAiProjectReviewDetail]

# 📺 Prototype 디자인
- [https://www.figma.com/design/X2d8HP3Aguo0iIeg76886H/Smart-TV-(%EA%B3%B5%EC%9C%A0%EC%9A%A9)?node-id=0-1&t=F8I0A5JxhHvdLC4f-1]

# 🚀 Backend 사용 방법 (README.md)

## **🔹 0. FE & BE 연동 테스트 (Frontend & Backend Integration Test)**
### **📌 Requirements**
- **Python 3.13.2** 사용 *(다른 버전도 가능하나 테스트되지 않음)*
- 필수 파일:
  - `backend/hyub_google_cloud_key.json`
  - `backend/llm/.env`
  - 위 파일이 없을 경우 요청 필요.

### **📌 실행 방법**
```bash
pip install -r requirements.txt  # 필수 라이브러리 설치
python main.py  # Backend 서버 실행
```
- **백엔드 문서 접속 확인:** [http://localhost:8000/docs](http://localhost:8000/docs)
- **연동 테스트:**  
  ```bash
  python ./tools/test_modified_backend.py  # 모든 status code가 200(성공)인지 확인
  ```

---

## **🔹 1. 주요 파일 설명**
| **파일명** | **설명** |
|------------|---------|
| `requirements.txt` | Python 3.13.2 환경의 필수 라이브러리 목록 (`pip install -r requirements.txt` 실행) |
| `main.py` | **FastAPI 기반 Backend 서버** 실행 파일 |
| `database.py` | **SQLAlchemy** 기반 DB 초기화 스크립트 |
| `app_data.db` | **SQLite3** 데이터베이스 파일 |
| `tools/make_toy_db.py` | **실험용 DB 생성 스크립트** |

---

## **🔹 2. DB Setup 및 사용 방법**
📌 *(크롤링 작업 후 DB를 새로 생성할 예정!)*

### **📌 DB 생성**
```bash
python database.py  # app_data.db 생성 (이미 존재하면 실행되지 않음)
```

### **📌 SQLite3을 사용한 DB 접근 방법**
```bash
sqlite3 app_data.db  # DB 접속 방법 1 (터미널)
```
또는 **DB Browser for SQLite** 사용 (GUI 기반 DB 조회 가능).

### **📌 주요 DB 명령어**
```sql
.tables;                           -- 테이블 목록 조회
PRAGMA table_info(<table>);        -- 특정 테이블의 컬럼 정보 확인
DROP TABLE IF EXISTS <table>;      -- 테이블 삭제
SELECT * FROM <table>;             -- 특정 테이블의 모든 데이터 조회
```

### **📌 DB 추가/삭제 작업**
```bash
python modify_db.py  # DB 추가/삭제 매크로 실행 (파일 직접 수정 필요)
```

---

## **🔹 3. Backend Server 실행**
```bash
python main.py  # Backend 서버 실행 (http://localhost:8000)
```

---

## **🔹 4. `app_data.db`**
- (추후 작업 예정)

---

## **🔹 5. `tools/`**
- (추후 작업 예정)

---

## **🔹 6. 크롤링 (Crawling)**
### **📌 크롤링 실행 방법**
1. **`chromedriver.exe` 설치**  
   *(웹 크롤링을 위한 필수 요소)*
2. **`crawling/` 디렉토리로 이동**
   ```bash
   cd crawling/
   ```
3. **크롤링 실행**
   ```bash
   python cloth.py
   ```

### **📌 크롤링 데이터 검사**
| 파일명 | 설명 |
|--------|------|
| `check_valid_image_2_csv.py` | 사진이 2개 이상 있는 데이터를 찾음 |
| `check_valid_image_4_csv.py` | 사진이 4개 있는 데이터를 찾음 |

---

## **🚀 추가 사항**
📌 **백엔드 서버 및 DB 관련 추가 작업 예정**  
📌 **크롤링 및 데이터 처리 자동화 업데이트 예정**

---

**🎯 프로젝트 업데이트 시 해당 README.md를 유지보수하세요!** 🚀  
📌 **문의 사항은 Issue를 등록하거나 팀원에게 연락하세요.** 😊
