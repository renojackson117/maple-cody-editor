# 메이플 코디 편집기 — 직접 호스팅용

최신 배포본: Aseprite 레이어 분리 저장, 서 있기·경계 핑퐁 재생 포함.

## 호스팅
ZIP을 풀고 index.html, JS/CSS, JSON, assets/, templates/를 같은 상대 경로 그대로 정적 웹 호스팅에 올리면 됩니다. index.html이 웹 루트에 오도록 배치하세요. 별도 설치·빌드·서버 API·로그인이 필요 없습니다.

GitHub Pages 등에 사용할 수 있습니다. 저장소에 ZIP 파일 자체가 아니라 압축을 푼 파일과 폴더 전체를 올리세요. .nojekyll도 함께 포함되어 있습니다.

## 내 컴퓨터에서 실행
이 폴더에서 다음 명령을 실행하세요.

    python -m http.server 8000

브라우저에서 http://localhost:8000 으로 접속하세요. index.html을 더블클릭해 file://로 열면 JSON 및 PSD 템플릿을 읽지 못할 수 있습니다.

## 주요 파일
- index.html: 화면
- style.css: 디자인
- app.js: 캐릭터·이펙트·재생
- editor.js: 픽셀 편집·레이어·Aseprite 저장
- psd.js: 규격 PSD 입출력
- character.json / skills.json / assets/: 추출 데이터와 이미지
- templates/Avatar_Cape.psd: 공식 망토 원본 템플릿

원본 WZ는 필요하지 않습니다. 이 ZIP에는 웹에서 사용하는 추출 데이터가 모두 들어 있습니다.

PSD 업로드는 공식 망토 시트(2750×3500, 8비트 RGB)를 대상으로 합니다. 편집기 레이어는 PSD 저장 시 규격 망토 레이어로 합성되고, Aseprite 저장 시 분리되어 저장됩니다.


v1.5.3: 한손/두손/폴암 휘두르기, 찌르기, 엎드려 공격에 기본 공격 궤적 추가. 기본 공격에 다른 스킬을 자동 연결하지 않음. 궤적은 WZ 원본이 아닌 캔버스 재현이며 동작 프레임, 재생 속도, 일시정지, 좌우 반전에 연동됨.


v1.5.4: 선택 영역 Ctrl+C 이미지 복사 추가. 활성 레이어의 선택된 픽셀만 투명 PNG로 복사하며 사각/올가미/같은 색 선택에 적용. HTTPS 또는 localhost의 이미지 클립보드 지원 브라우저 필요.


v1.5.5: v1.5.3의 임의 캔버스 궤적 제거. 제공된 KMS v55 Character.wz/Afterimage에서 PNG 및 origin, delay, a0/a1, 모션 발동 프레임을 직접 추출. 한손 swordOL/0, 두손 swordTL/0, 폴암 poleArm/0 기본 프리셋 사용. 무기 선택 기능이 없으므로 특정 착용 무기 자동 판별은 하지 않음. 위치는 캐릭터 좌표에서 WZ origin만 차감하며 임의 위치 보정 없음. Ctrl+C 수정 유지.
