# 위협 그룹 별칭 매핑

벤더마다 명명 규칙이 다르므로(Microsoft `*Typhoon`, Mandiant `UNC`/`APT`, Cisco Talos `UAT`, CrowdStrike `*Panda` 등) 이 표는 실행마다 누적·갱신됩니다.

| 대표명 | Microsoft | APT 번호 | Mandiant | 기타 | 귀속 | 마지막 관측 |
|---|---|---|---|---|---|---|
| Mustang Panda | Twill Typhoon | TA416 | UNC6384 | HoneyMyte(Kaspersky), Earth Preta(Trend Micro), RedDelta/BRONZE PRESIDENT/STATELY TAURUS 등(MITRE G0129) | 귀속 미확인 — China-nexus/Chinese-linked (검색 스니펫, 미검증) | 2026-08 |
| UNC6508 | - | - | UNC6508 | - | 귀속 미확인 — 출처 원문: "PRC-nexus threat actor" (GTIG) | 2026-06 |
| UAT-7810 | - | - | - | LapDogs ORB 운영자 (Cisco Talos) | 귀속 미확인 — China-nexus (검색 스니펫, 미검증) | 2026-07 |
| 미상 (CVE-2026-59310 vCenter 캠페인) | - | - | - | - | 귀속 미확인 — Chinese-speaking, moderate confidence (검색 스니펫, 미검증) | 2026-08 |
| 미상 (SilkParasite) | - | - | - | Bitdefender 명명 | 귀속 미확인 — China-Nexus APT, medium confidence (검색 스니펫, 미검증) | 2026-08 |
| Jewelbug | - | - | - | Earth Alux(Trend Micro), REF7707(Elastic), CL-STA-0049(Palo Alto) | 귀속 미확인 — China-based (검색 스니펫, 미검증) | 2026-08 |
| APT24 | - | APT24 | APT24 | - | 귀속 미확인 — 원문: "People's Republic of China (PRC)-nexus threat actor" (GTIG, 검증) | 2025-09(캠페인)/2025-11(공개) |

## 비고
- 2026-08-27 실행: SilkParasite(Bitdefender, 공개일 2026-08-19, 중앙아시아 정부기관 대상)와 Jewelbug(Symantec/security.com, 공개일 2026-08-13경, 첩보+암호화폐 사기 이중운영)를 신규 미검증 후보로 추가(둘 다 60일 창 안, 원문 EGRESS_BLOCKED로 미검증). APT24(GTIG, BADAUDIO 캠페인, 공개일 2025-11-20)를 이번 실행에서 최초로 원문 확보 — 캠페인 자체는 60일 창 밖이라 "최근 캠페인" 절에는 미포함하되, 신규 검증 그룹으로 표에 추가하고 C2 도메인 16건·SHA-256 해시 8건을 검증 IOC로 `blocklists/domains.txt`에 반영(UNC6508 사례와 동일한 처리 관례). 기존 4건의 미검증 후보(CoolClient/HoneyMyte, FDMTP/Twill Typhoon, UAT-7810/LapDogs, CVE-2026-59310 vCenter)는 관련 1차 출처가 이번 실행에서도 전부 차단되어 상태 변화 없음.
- 2026-08-26 실행: 신규 캠페인·신규 그룹(표 등재) 없음. 검색으로 두 건의 신규 후보를 확인했으나 60일 캠페인 창 밖이라 표에는 등재하지 않고 참고용으로만 기록: (1) CL-STA-1062(TinyRCT 백도어, Palo Alto Unit 42, 공개일 2026-06-26 — UAT-7237(Cisco Talos, 2025-08)과 오버랩, 귀속 미확인/China-speaking 검색 스니펫, 원문 미페치·미검증), (2) GopherWhisper(ESET, 공개일 2026-04-23, 몽골 정부기관 대상, 귀속 미확인/China-aligned 검색 스니펫, 원문 미페치·미검증). 기존 4건의 미검증 후보(CoolClient/HoneyMyte, FDMTP/Twill Typhoon, UAT-7810/LapDogs, CVE-2026-59310 vCenter)의 원문 확보를 재시도했으나 관련 1차 출처가 전부 EGRESS_BLOCKED로 여전히 차단되어 상태 변화 없음. 신규 벤더 도메인 리치버빌리티 프로브(Unit42, Trend Micro, Recorded Future, SC World, Hive Pro) 5건도 전부 차단됨.
- 2026-08-25 실행: 신규 캠페인·신규 그룹 없음. 전일 식별한 4건의 미검증 후보(HoneyMyte/CoolClient, Twill Typhoon/FDMTP, UAT-7810/LapDogs, CVE-2026-59310 vCenter 미상 행위자)의 원문 확보를 재시도했으나 관련 1차 출처(Securelist, Darktrace, Cisco Talos, SecurityScorecard, Medium/QUIRSO 등)가 전부 EGRESS_BLOCKED로 여전히 차단되어 상태 변화 없음.
- 2026-08-24 실행: Mustang Panda(HoneyMyte/Twill Typhoon 별칭)를 신규 추가. CoolClient 커널 루트킷(Securelist, 2026-08-17 공개)과 FDMTP 백도어 APJ 캠페인(Darktrace, 2026-08-04 공개) 모두 원문 페치가 차단되어 전량 미검증. 별칭 목록은 MITRE ATT&CK G0129 그룹 페이지 검색 스니펫을 참고했으며(attack.mitre.org 자체는 미페치), 향후 원문 확인 시 정정될 수 있음.
- 2026-08-24 실행: UNC6508(REDCap/INFINITERED 캠페인)은 원 보고서 공개일(2026-06-15)이 60일 창을 벗어나 이번 스냅샷의 "최근 캠페인" 절에서는 제외되었으나, 그룹 자체는 표에 계속 유지(누적). 관련 IOC(IP 23.169.65.49)는 `blocklists/ips.txt`에 유지됨.
- 이번 실행에서 새로 확인했으나 최근 60일 캠페인 창을 벗어나 이번 스냅샷의 "최근 캠페인" 절에는 포함하지 않은 그룹(참고용, 표에는 미등재): UAT-8302(Cisco Talos, 2026-05-05 공개), Salt Typhoon/OPERATOR PANDA/RedMike/UNC5807/GhostEmperor(CISA AA25-239A, 2025-08-27 공개), Earth Estries(Trend Micro GhostSpider/Masol RAT, 2024년 보고서), UNC2814/GRIDTIDE(Google GTIG, 2026년 2월 공개, Google Sheets를 C2로 악용해 42개국 53개 조직 침해), Salt Typhoon 미 하원 위원회 이메일 침해(2026-01 보도), Mustang Panda LOTUSLITE 베네수엘라 테마 스피어피싱(2026-01 공개). 향후 실행에서 이들에 대한 신규(60일 이내) 보고서를 확인하면 표에 추가합니다.
- 귀속 표기 원칙: 이 실행에서 성공적으로 페치한 출처가 명시적으로 PLA 또는 MSS를 언급하지 않는 한 "귀속 미확인"으로 표기합니다. 대부분의 벤더는 "PRC-nexus" 또는 "China-nexus"라는 일반 표현만 사용합니다.
