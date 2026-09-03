# China-APT-Tracker

중국 국가 배후(PLA/MSS 연계로 공개 출처가 명시적으로 밝힌 경우만) 위협 그룹의 최근 캠페인을 방어/차단 목적으로 추적하는 자동화 리포지토리입니다. 모든 데이터는 공개된 벤더·정부 위협 인텔리전스 보고서에서만 수집합니다.

- **마지막 갱신**: 2026-09-03 UTC
- **검증된 도메인**: 22
- **검증된 IP**: 7
- **미검증 도메인**: 0
- **미검증 IP**: 0
- **파일 해시(SHA-256/MD5)**: 19 (최신 스냅샷 기준, APT24/BADAUDIO 8건 + UNC2814/GRIDTIDE 6건 + Mustang Panda(UNC6384) 5건 — UNC6508 관련 해시 7건은 캠페인이 60일 창을 벗어나 `latest.md`에서는 제외, [`snapshots/2026-08-23.md`](snapshots/2026-08-23.md)에 보존)
- **악용 CVE**: 12 (검증 7 — Silk Typhoon/HAFNIUM, MSTIC 원문 확보 / 미검증 5 — 원문 페치 차단으로 검색 스니펫만 확보)

## 최신 리포트
- [`latest.md`](latest.md) — 가장 최근 스냅샷 전문
- [`snapshots/`](snapshots/) — 날짜별 과거 스냅샷 아카이브

## 차단 리스트 (Raw URL)
방화벽/DNS 싱크홀에 바로 투입 가능한 파일은 아래 두 개뿐입니다. 나머지(`unverified-*.txt`, `exploited-cves.txt`)는 검증되지 않았거나 IOC가 아니므로 직접 차단에 사용하지 마십시오.

- 도메인(검증): https://raw.githubusercontent.com/cisspco/China-APT-Tracker/main/blocklists/domains.txt
- IP(검증): https://raw.githubusercontent.com/cisspco/China-APT-Tracker/main/blocklists/ips.txt
- 도메인(미검증, 참고용): https://raw.githubusercontent.com/cisspco/China-APT-Tracker/main/blocklists/unverified-domains.txt
- IP(미검증, 참고용): https://raw.githubusercontent.com/cisspco/China-APT-Tracker/main/blocklists/unverified-ips.txt
- 악용 CVE 목록: https://raw.githubusercontent.com/cisspco/China-APT-Tracker/main/exploited-cves.txt
- 그룹 별칭 매핑: https://raw.githubusercontent.com/cisspco/China-APT-Tracker/main/groups.md

> **`blocklists/domains.txt`와 `blocklists/ips.txt`만 방화벽에 직접 투입해도 안전합니다.** 나머지 파일은 미검증 정보 또는 IOC가 아닌 CVE/그룹 메타데이터입니다.

## 방법론
- 매일 자동 실행되어 벤더/정부 보고서를 검색·수집하고, 성공적으로 원문을 페치한 경우만 "검증"으로 분류합니다.
- 검색 결과 스니펫에서만 확인되었거나 원문 페치가 차단된 경우 "미검증"으로 분류하며 검증 목록에 절대 포함하지 않습니다.
- PLA/MSS 귀속은 페치에 성공한 출처가 명시적으로 해당 국가 조직을 지목한 경우에만 표기합니다. 그 외에는 "귀속 미확인"으로 표기하고 출처의 원문 표현을 그대로 인용합니다.
