# 딱 하나

칠판 카드와 내 카드에서 **겹치는 그림 딱 하나**를 먼저 찾는 교실용 실시간 게임입니다.

- 주소: https://dobbi52.github.io/ddak-hana/
- 선생님이 전자칠판에서 방을 만들면, 학생들이 휴대폰·노트북으로 QR이나 방 코드로 들어옵니다.
- **개인전**: 맞힌 순서대로 5·3·2·1점
- **보스전**: 반 전체가 함께 보스 3마리(슬라임 왕·바위 골렘·불꽃 드래곤)를 공격
- **이벤트 라운드**: 그림자·빙글빙글·황금(점수 두 배) 라운드가 한 판에 3번
- **혼자 연습**: 점수 도전 / 보스전, 그림 8개(보통)·6개(쉬움)
- 도트 그림 57개, 어느 두 카드든 겹치는 그림은 정확히 하나

## 서버 (Firebase Realtime Database)

프로젝트 `ddak-hana`, 규칙:

```json
{
  "rules": {
    "rooms": { "$code": { ".read": true, ".write": true } },
    "presence": { ".read": true, "$id": { ".write": true } }
  }
}
```

`presence`는 생각 오락실(https://dobbi52.github.io/games/)에 '접속 중' 인원을 보여 주는 데 씁니다.

Made by dobbi
