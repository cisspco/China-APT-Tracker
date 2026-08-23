# 위협 그룹 별칭 매핑

벤더마다 명명 규칙이 다르므로(Microsoft `*Typhoon`, Mandiant `UNC`/`APT`, Cisco Talos `UAT`, CrowdStrike `*Panda` 등) 이 표는 실행마다 누적·갱신됩니다.

| 대표명 | Microsoft | APT 번호 | Mandiant | 기타 | 귀속 | 마지막 관측 |
|---|---|---|---|---|---|---|
| UNC6508 | - | - | UNC6508 | - | 귀속 미확인 — 출처 원문: "PRC-nexus threat actor" (GTIG) | 2026-06 |
| UAT-7810 | - | - | - | LapDogs ORB 운영자 (Cisco Talos) | 귀속 미확인 — China-nexus (검색 스니펫, 미검증) | 2026-07 |
| 미상 (CVE-2026-59310 vCenter 캠페인) | - | - | - | - | 귀속 미확인 — Chinese-speaking, moderate confidence (검색 스니펫, 미검증) | 2026-08 |

## 비고
- 이번 실행에서 새로 확인했으나 최근 60일 캠페인 창을 벗어나 이번 스냅샷의 "최근 캠페인" 절에는 포함하지 않은 그룹(참고용, 표에는 미등재): UAT-8302(Cisco Talos, 2026-05-05 공개), Salt Typhoon/OPERATOR PANDA/RedMike/UNC5807/GhostEmperor(CISA AA25-239A, 2025-08-27 공개), Earth Estries(Trend Micro GhostSpider/Masol RAT, 2024년 보고서). 향후 실행에서 이들에 대한 신규(60일 이내) 보고서를 확인하면 표에 추가합니다.
- 귀속 표기 원칙: 이 실행에서 성공적으로 페치한 출처가 명시적으로 PLA 또는 MSS를 언급하지 않는 한 "귀속 미확인"으로 표기합니다. 대부분의 벤더는 "PRC-nexus" 또는 "China-nexus"라는 일반 표현만 사용합니다.
