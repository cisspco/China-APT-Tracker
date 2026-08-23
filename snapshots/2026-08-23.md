# China State APT Campaign Snapshot — 2026-08-23 UTC

## 수집 상태
- 페치 성공: https://cloud.google.com/blog/topics/threat-intelligence/prc-targets-us-medical-research (2026-06-15, Google Threat Intelligence Group), https://www.microsoft.com/en-us/security/blog/threat-intelligence/threat-actors/ (인덱스 페이지, 최근 60일 내 중국 관련 신규 게시물 없음)
- 페치 차단(EGRESS_BLOCKED): blog.talosintelligence.com, www.darkreading.com, socradar.io, securityboulevard.com, www.gat.report, www.darktrace.com
- 검증된 IOC: 8 개 / 미검증 IOC: 0 개 (도메인·IP 기준 — 미검증 CVE 5건 별도)

이번 실행에서는 8건의 WebFetch 예산을 모두 소진했으며, 완전히 성공한 것은 Google Cloud(GTIG) 게시물 1건뿐입니다. VMware vCenter(CVE-2026-59310) 캠페인과 UAT-7810 LONGLEASH ORB 캠페인은 검색 스니펫에서만 확인되어 본문을 직접 페치하지 못했으므로 전량 미검증(⚠️)으로 표시합니다.

## 최근 캐페인 (최근 60일)

### REDCap 표적 의료·학술·군사 연구 캠페인 — UNC6508
- 귀속: 귀속 미확인 — 출처 원문 표현: "People's Republic of China (PRC)-nexus threat actor"; 특정 PLA/MSS 조직으로의 귀속은 명시되지 않음. (Google Threat Intelligence Group)
- 대상: 의료 연구기관, 학술기관, 군 의료·연구기관, 보건 규제기관 — 미국·캐나다
- 초기 침투: 공개 노출된 REDCap(Research Electronic Data Capture) 서버의 구버전 취약점 익스플로잇, 다운그레이드 공격 (특정 CVE 미공개)
- 주요 도구/멀웨어: INFINITERED (드로퍼/업그레이드 가로채기, 자격증명 수집기, 백도어 3개 모듈)
- 관측 시점: 2023-09 ~ 2025-11 (장기 활동, 보고서는 2026-06-15 게시)
- 출처: [Public and Private Medical Community Targeted by China-Nexus Threat Actor](https://cloud.google.com/blog/topics/threat-intelligence/prc-targets-us-medical-research) — Google Threat Intelligence Group, 2026-06-15 (fetched)

### CVE-2026-59310 VMware vCenter 글로벌 익스플로잇 캠페인 🔥 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 스니펫상 출처(QUIRSO GmbH IR팀) 표현: "moderate confidence that the exploitation campaign is operated by a Chinese-speaking threat actor, likely working in the UTC+08:00 time zone" — PLA/MSS 언급 없음. 원문 미페치로 전량 미검증.
- 대상: 글로벌 vCenter 운영 조직 — 47개국 361개 IP 확인 (독일, 미국, 튀르키예, 이란, 프랑스 집중)
- 초기 침투: VMware vCenter 디렉터리 트래버설 취약점(CVE-2026-59310, CVSS 9.8) 익스플로잇, 패치(2026-07-29) 공개 5일 만에 익스플로잇 시작(2026-08-03)
- 주요 도구/멀웨어: ForestTiger, Troy 백도어, linuxFile 백도어, reverse_ssh 바이너리, 일부 사례 Babuk 파생 랜섬웨어
- 관측 시점: 2026-08 (진행 중)
- 출처: 검색 스니펫만 확인 — QUIRSO GmbH(Medium, 차단), TheHackerNews(차단 목록), SecurityWeek(차단 목록), Dark Reading(차단), Security Boulevard(차단) — 모두 EGRESS_BLOCKED로 원문 미확인

### UAT-7810 LONGLEASH ORB(LapDogs) 네트워크 확장 캠페인 🔥 ⚠️ (미검증)
- 귀속: 귀속 미확인 — Cisco Talos가 "China-nexus" / UAT(uncategorized threat actor) 명칭으로만 분류, PLA/MSS 명시 없음(검색 스니펫 기준, 원문 미페치)
- 대상: 미상 (Ruckus/ASUS AiCloud 라우터를 통한 ORB 인프라 확장 — 특정 피해 산업군 스니펫에 미기재)
- 초기 침투: Ruckus 라우터 n-day 취약점(CVE-2020-22653, CVE-2020-22658, CVE-2023-25717), ASUS AiCloud 라우터(CVE-2025-2492)
- 주요 도구/멀웨어: LONGLEASH(업그레이드된 ORB 백도어), DOGLEASH(경량 리눅스 백도어), JARLEASH(Java 기반 파일관리/FTP/SFTP/Netcat 유틸리티), LEASHTEST(MIPS IoT 검증 도구)
- 관측 시점: 2026-07-07 (Cisco Talos 공개일)
- 출처: 검색 스니펫만 확인 — Cisco Talos(blog.talosintelligence.com, 차단), TheHackerNews(차단 목록), SOCRadar(차단), gat.report(차단) — 모두 EGRESS_BLOCKED로 원문 미확인

## 그룹 별칭 매핑
| 대표명 | Microsoft | APT 번호 | Mandiant | 기타 | 귀속 |
|---|---|---|---|---|---|
| UNC6508 | - | - | UNC6508 | - | 귀속 미확인 (PRC-nexus, GTIG) |
| UAT-7810 | - | - | - | LapDogs ORB 운영자 (Cisco Talos 명칭) | 귀속 미확인 (China-nexus, 미검증) |
| 미상 (CVE-2026-59310 vCenter 캠페인) | - | - | - | - | 귀속 미확인 (Chinese-speaking, moderate confidence, 미검증) |

## 악용 CVE (패치 우선순위)
- CVE-2026-59310 — VMware vCenter Server (CVSS 9.8), 미상(China-nexus 추정) 캠페인, 출처: 검색 스니펫만(QUIRSO GmbH, 미검증) ⚠️ (미검증)
- CVE-2020-22653 — Ruckus 라우터, UAT-7810, 출처: 검색 스니펫만(Cisco Talos, 미검증) ⚠️ (미검증)
- CVE-2020-22658 — Ruckus 라우터, UAT-7810, 출처: 검색 스니펫만(Cisco Talos, 미검증) ⚠️ (미검증)
- CVE-2023-25717 — Ruckus 라우터, UAT-7810, 출처: 검색 스니펫만(Cisco Talos, 미검증) ⚠️ (미검증)
- CVE-2025-2492 — ASUS AiCloud 라우터, UAT-7810, 출처: 검색 스니펫만(Cisco Talos, 미검증) ⚠️ (미검증)

## C2 도메인 (0)
없음 (검증/미검증 모두 도메인 IOC 확보 실패 — 원문 미페치로 인한 공백)

## C2 IP (1)
- 23.169[.]65[.]49 — 침해된 ASUS 라우터, 관리자 로그인 출처, UNC6508 / REDCap 캠페인, 출처: Google Threat Intelligence Group (fetched)

## 파일 해시 (7)
### SHA-256
- ba6b73b0ca0dc7f86b3b397893ac32d729fd53f9df20643288f141f29d020af7 — help.php 웹셸(퍼시스턴스), UNC6508, GTIG
- db65c1b9f9e4cb4d729f45ad4b6fcf3e277caf9eb4c875425dec93fd883f9136 — 자격증명 수집기, UNC6508, GTIG
- c1ac43d23f89d41eb4ff131678ab562ab2cfed9aa334b13767ef141d303b0e5b — 자격증명 수집기, UNC6508, GTIG
- 8f0158855a656b629ca76ebca565f18bc25563ded34b65d6771632c20edb68ec — INFINITERED 백도어, UNC6508, GTIG
- 51a57bfc9ed3eb6451c1c289607814d59e1698c666fb97ac5f694c398f23d045 — INFINITERED 백도어, UNC6508, GTIG
- 4efbef69eb3b09bacff892d6a55778d07c418e7f15eba3cf1245e8cdfd8dda0b — INFINITERED 드로퍼, UNC6508, GTIG
- 58bb25777e0aa86bcd2125101e0bca4e8732b03d91bd8d2f205b446a2a8d5c86 — INFINITERED 드로퍼, UNC6508, GTIG

### MD5
없음

## 호스트 IOC · LOTL 아티팩트
- `help.php` — REDCap 서버에 배치된 웹셸(퍼시스턴스), UNC6508
- 쿠키 파라미터 `REDCAP-TOKEN` — INFINITERED 백도어 C2 명령 전달 채널, UNC6508
- Google Workspace 콘텐츠 규정 준수 규칙 이름 `"Patroit"`(오타 원문 그대로) — 정상 기능을 악용한 은밀한 BCC 이메일 전달, UNC6508
- GUID `b49e334d-9c01-463e-9bc5-00a6920fb66e` — INFINITERED 코드 내 구분자, UNC6508
- `reverse_ssh` 바이너리 배치 — vCenter 침해 후 지속 접근 확보, 미상 China-nexus 추정 캠페인(미검증)
- `linuxFile` 백도어 — vCenter 침해 사례, 미상 China-nexus 추정 캠페인(미검증)

## 이번 실행 변경사항
- 신규 캐페인: UNC6508(REDCap/INFINITERED, 검증), CVE-2026-59310 vCenter 캠페인(미검증), UAT-7810 LONGLEASH(미검증)
- 신규 IOC: SHA-256 7건 + IP 1건 (검증), CVE 5건 (미검증)
- 제거: 없음
- 승격(미검증→검증): 없음
- 귀속 변경: 없음 (최초 실행)

## 차단 운영 포맷 (복붙용)

### Domain blocklist (un-defanged, one per line)
```
(없음 — 이번 실행에서 검증된 도메인 IOC 없음)
```

### IP blocklist (un-defanged, one per line)
```
23.169.65.49
```

## 출처
- [Public and Private Medical Community Targeted by China-Nexus Threat Actor Pursuing AI, Cyber, Medical, and National Defense Research](https://cloud.google.com/blog/topics/threat-intelligence/prc-targets-us-medical-research) — 2026-06-15 — fetched
- [Microsoft Security Blog — Threat actors index](https://www.microsoft.com/en-us/security/blog/threat-intelligence/threat-actors/) — 조회일 2026-08-23 — fetched (최근 60일 내 신규 중국 관련 게시물 없음)
- UAT-8302 (Cisco Talos, 2026-05-05) — 검색 스니펫만, 60일 창 밖으로 이번 보고서에서 제외
- CVE-2026-59310 관련: QUIRSO GmbH(Medium) / TheHackerNews / SecurityWeek / Dark Reading / Security Boulevard — blocked (EGRESS_BLOCKED), 검색 스니펫만 확인
- UAT-7810 LONGLEASH 관련: Cisco Talos(blog.talosintelligence.com) / TheHackerNews / SOCRadar / gat.report — blocked (EGRESS_BLOCKED), 검색 스니펫만 확인
