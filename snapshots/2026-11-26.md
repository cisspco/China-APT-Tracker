# China State APT Campaign Snapshot — 2026-11-26 UTC

## 수집 상태
- 페치 성공: [Microsoft — What defenders need to know about ARTEX, the agentic AI framework threat actors abuse](https://www.microsoft.com/en-us/security/blog/2026/11/25/what-defenders-need-to-know-artex-agentic-ai-framework-threat-actors-abuse/)(2026-11-25, 신규 페치); [GTIG AI Threat Tracker: Agentic Threat Activity Crosses a Significant Threshold](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold)(2026-11-16, 재페치 — PentAGI 프레임워크 세부사항 신규 확인); [Microsoft Security Blog 메인 색인](https://www.microsoft.com/en-us/security/blog/)(재확인); [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence)(재확인)
- 페치 차단(EGRESS_BLOCKED/ENOTFOUND): blog.talosintelligence.com(UAT-11473/KeyDrift 원문), labs.cloudsecurityalliance.org(KeyDrift 연구노트), blog.lumen.com(Volt Typhoon "Silent Train" 원문), cloud.google.com/.../llmjacking-monetizing-compromised-cloud-models(경로 오류로 재시도 필요 — 아래 비고 참조)
- 검증된 IOC: 신규 0개(누적 도메인 35·IP 42, 변동 없음) / 미검증 IOC: 신규 0개(누적 도메인 0·IP 0) / 신규 CVE: 0건(누적 29건, 검증 13/미검증 16)

6개 정기 WebSearch 쿼리를 수행했습니다. Microsoft가 2026-11-25에 공개한 ARTEX 방어자 가이드에서 신규 그룹명 Crystal Typhoon을 처음 확인했고, 기존에 알려진 Salt Typhoon도 ARTEX 사용 행위자 목록에 포함되어 있음을 확인했습니다(구체 캠페인·CVE·IOC는 원문에 미기재). GTIG AI Threat Tracker(2026-11-16)를 재페치한 결과 기존에 반영하지 못했던 PentAGI 프레임워크(아시아 전역 다수 조직 대상, 2026년 8월 말~10월 초 활동) 세부사항을 추가로 확인했습니다. 그 외 Cisco Talos(UAT-11473/KeyDrift)·Lumen Black Lotus Labs(Volt Typhoon "Silent Train")·CSA 연구노트는 전량 ENOTFOUND로 재확보 실패해 기존 미검증 상태 유지. GTIG "The Rise of LLMJacking"(2026-11-02)은 금전적 동기 활동으로 서술되고 중국 귀속 문구가 확인되지 않아 미채택. APT41/UNC6508의 Cisco SD-WAN(CVE-2026-20245) 연계설은 2차 보도에서도 명확히 확인되지 않아(사이드바 링크 수준) 미채택.

60일 창이 2026-09-27~로 이동했습니다. NeedyMantis(원문 공개 2026-09-28)를 포함해 기존 10건 캠페인 모두 창 내 유지됩니다. 7일 창(2026-11-19~2026-11-26) 기준 ARMORY CASTLE/vCenter(11-19)에 더해 Storm-0940/ARTEX 방어자 가이드(11-25)가 신규로 🔥 대상에 포함됩니다(단, 이 가이드 자체는 신규 캠페인이 아니라 기존 Storm-0940/ARTEX 캠페인 항목에 대한 보강 정보).

## 최근 캠페인 (최근 60일)

### ARMORY CASTLE(구 UNC5221) — VMware vCenter 제로데이(CVE-2026-123890) 추가 익스플로잇, SLIMSAVAGE·BONESAW·LAZYBONES 등 신규 툴셋 🔥
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음.
- 대상: 불명 — 원문은 "a high-priority environment"로만 서술, 구체 산업·국가 미기재
- 초기 침투: BeyondTrust Remote Support(구 Bomgar) 제로데이 CVE-2026-102764(기존 2026-10-15 공개) 경유 침투 → 내부 Linux 어플라이언스로 측면이동 → VMware vCenter 제로데이 CVE-2026-123890(인증 없는 SRP-6a 세션키 노출, DCE/RPC 2012포트, administrator@vsphere.local 인증우회) 추가 익스플로잇
- 주요 도구/멀웨어: SLIMSAVAGE(JSP 웹셸 `ActiveSer.jsp`), CAGEMATCH(JSP 파일스테이징 웹셸 `u.jsp`), BEARBONES(백도어 Dropbear SSH `/tmp/dbr`, TCP 53·33992 리슨), BONESAW(Go 익스플로잇 유틸 `/tmp/123`), SAWSNAKE(Go SAML 유틸 `/tmp/sss`, Golden SAML 위조), LAZYBONES(Go 백도어 `/usr/bin/vmtoolscs`, Slack API C2), vmfs_browser.py(VMFS 볼륨 추출)
- 관측 시점: BONESAW 실행 2026년 9월 초, CVE-2026-123890 공개 2026-11-19
- 출처: [GTIG](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere) — 2026-11-19 — fetched(이전 실행)

### Storm-0940(UNC7228) — ARTEX AI 에이전트 기반 ConnectWise 공급망 침해, M365 테넌트 대량 표적화 🔥
- 귀속: 귀속 미확인 — 원문 인용: "China-state aligned actor"(Microsoft, 검증) / "PRC-nexus actor STORM-0940"(GTIG 인용, 검증). Microsoft 2026-11-25 방어자 가이드는 행위자 전반을 "state-sponsored and financially monitored threat actors"로만 일반화 서술. PLA/MSS 명시 없음.
- 대상: 항공우주·국방, 자동차, 화학, 에너지, 금융서비스, 정부, 법률, 제조, 미디어, 군, 반도체, 소프트웨어, 기술, 싱크탱크·비영리단체 등 전 세계 수백 개 조직. ConnectWise Cloud Backup 멀티테넌트 앱 통해 2,250개 이상 M365 테넌트 대상화.
- 초기 침투: ConnectWise Cloud Backup 멀티테넌트 앱 공급망 침해 → 신뢰된 OAuth 앱 경유. 2026-10-10~14 패스워드 스프레이(단일 캠페인에서 실패 로그인 151,000건 이상, 분당 최대 2,900건 — Microsoft 2026-11-25 보강). CVE 명시 없음
- 주요 도구/멀웨어: ARTEX(오픈소스 멀티에이전트 LLM 펜테스트 프레임워크, Go+Next.js, 2026-07 오픈소스 공개 → 2026-10 원 개발자 소스 삭제 → 중국 소재 ThreatBook이 소유권 주장하며 "ARTEX Pro" 상용판 판매 시작), 웹셸 `cl1217.jsp` 등. Microsoft는 Storm-0940 외에도 Storm-3358(캄보디아 소재, 금전적 동기, 금융권 표적), Onyx Sleet, Pearl Sleet, **Crystal Typhoon(신규 확인 그룹명)**, **Salt Typhoon**도 ARTEX를 도구체계에 통합했다고 서술(구체 캠페인·CVE·IOC는 미기재)
- 관측 시점: 최소 2026-08말부터, 2026-10-21 Microsoft 공개, 2026-10-30 GTIG/Mandiant 보강 공개, 2026-11-25 Microsoft 방어자 가이드 추가 보강
- 출처: [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — 2026-10-21 — fetched(이전 실행); [GTIG/Mandiant](https://cloud.google.com/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — 2026-10-30 — fetched(이전 실행); [Microsoft — ARTEX 방어자 가이드](https://www.microsoft.com/en-us/security/blog/2026/11/25/what-defenders-need-to-know-artex-agentic-ai-framework-threat-actors-abuse/) — 2026-11-25 — fetched(금일 신규)

### LEAKY CASTLE(PRC 계약업체) 및 CAIRN·PentAGI 프레임워크 — AI/LLM 기반 사이버첩보 활동, 미 항공우주 섹터·아시아 전역 표적
- 귀속: 귀속 미확인 — 원문 인용: "a PRC contractor"(LEAKY CASTLE, GTIG, 검증) / "PRC-nexus cyber espionage actors used LLM tools and models for reconnaissance, front-end scanning, researching targets across various sectors and geographies, and weaponizing exploits"(GTIG, 검증). PLA/MSS 명시 없음.
- 대상: LEAKY CASTLE — 원문에 특정 산업·국가 미기재. CAIRN 프레임워크 기반 활동 — 미국 항공우주 섹터. PentAGI 프레임워크 기반 활동(금일 재확인) — 아시아 전역 다수 조직("a wide range of organizations in Asia")
- 초기 침투: 불명 — LLM을 정찰, 공격표면 스캐닝, 타겟 리서치, 익스플로잇 무기화에 활용한 것으로만 서술
- 주요 도구/멀웨어: CAIRN(공격용 LLM 프레임워크), LEAKY CASTLE(PRC 계약업체 명칭), PentAGI(공격용 LLM 프레임워크, 금일 재확인)
- 관측 시점: 2026년 3분기(Q3 2026) 활동, PentAGI 활동은 2026-08말~10월초, 2026-11-16 GTIG 공개
- 출처: [GTIG AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold) — 2026-11-16 — fetched(금일 재페치, PentAGI 세부사항 신규 확인)

### CopperDragon(추정 공급자) / SilentDelivery·OceanGate·DarkWire — Sparrow 생태계 기반 3개 클러스터 공급망 추정 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합: "China-nexus intrusion clusters"(Check Point Research 재보도, 원문 research.checkpoint.com 미확보). "CopperDragon"은 Check Point 추정 공급자 명칭이며 3개 클러스터와의 관계는 "unconfirmed"로 서술됨. PLA/MSS 언급 없음.
- 대상: 통신사, 정부기관, 군, 연구기관, critical infrastructure 등 21개국
- 초기 침투: 불명 — 재보도에 구체 벡터·CVE 미기재
- 주요 도구/멀웨어: SquadC, AnnobinDoor, SparrowShell — Sparrow 프레임워크 기반 코드 유사성으로 FamousSparrow와의 연관성 시사되나 원문 미확보
- 관측 시점: 1년여 조사, 공개 2026-11-10경(Check Point)
- 출처: 검색 결과만 확인 — Check Point Research(미확보), 재보도([Infosecurity Magazine](https://www.infosecurity-magazine.com/news/chinese-malware-tied-three-hacking/), [TheHackerNews](https://thehackernews.com/2026/11/three-china-nexus-espionage-campaigns.html), [Cybernews](https://cybernews.com/security/new-global-china-cyber-espionage-campaign/))

### VAPOR PANDA — ARTEX/DeepSeek AI 에이전트 기반 글로벌 동시다발 침투 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "China-based targeted intrusion adversary"(CrowdStrike, 재보도 종합, 원문 미검증), 구 VexatiousTemper
- 대상: 정부부처, 통신사(미국·벨기에·필리핀), 제약·반도체·국방·원자력·금융 등 14개국 200개 이상 조직
- 초기 침투: 불명 — ARTEX를 DeepSeek 등으로 구동한 자동화된 정찰·침투(재보도)
- 주요 도구/멀웨어: ARTEX, BLOODALCHEMY 백도어
- 관측 시점: 캠페인 2026-10-17~10-28, 공개 2026-10-29~30
- 출처: 검색 결과만 확인 — CrowdStrike(DNS 미해석), 재보도(다수)

### UAT-11473(KeyDrift) — Cisco SD-WAN 제로데이, Volt Typhoon "Silent Train" 인프라 중첩 ⚠️ (미검증)
- 귀속: 귀속 미확인 — Talos 원문(재보도 종합)은 UAT-11473 자체에 국가 귀속 표현을 직접 사용하지 않음. "infrastructure overlaps considerably with Volt Typhoon's 'Silent Train'"로만 서술. PLA/MSS 언급 없음.
- 대상: 우주·위성 서비스, 국방·항공우주 기술, 정책 연구기관
- 초기 침투: CVE-2026-20127(Cisco Catalyst SD-WAN Controller, vSmart/vBond 인증 우회, CVSS 10.0)
- 주요 도구/멀웨어: KeyDrift 프레임워크 — PolyFlame(`libdssl.so`), LittleFilch(OpenSSL `SSL_read` 후킹)
- 관측 시점: 활동 "historical", 공개 2026-10-28(Cisco Talos). Lumen Black Lotus Labs는 별도로 Volt Typhoon의 "Silent Train" 중계 인프라(SOHO 라우터·IoT 장비 등 27개 이상 기기군 경유, 평균 4시간 세션)가 제로데이 최소 4건에 사용되었다고 2026-10-28 공개(원문 blog.lumen.com 금일도 ENOTFOUND로 미확보)
- 출처: 검색 결과만 확인 — Cisco Talos(차단), Lumen(차단), 재보도(일부 차단)

### ARMORY CASTLE(구 UNC5221) — BeyondTrust Remote Support 제로데이 익스플로잇, SAWFLY·BARECLAW
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음.
- 대상: 불명 — 원문에 특정 산업·국가 미기재
- 초기 침투: BeyondTrust Remote Support(구 Bomgar, 26.2.3 이하) 제로데이 CVE-2026-102764(인증 없는 임의 파일 업로드)
- 주요 도구/멀웨어: SAWFLY(PHP 웹셸 `mangoapi.php`), BARECLAW(SOCKS5-over-WebSocket 터널러 `ingredi_ws`)
- 관측 시점: 제로데이 익스플로잇 2026년 8월 말, 2026-10-15 공개
- 출처: [GTIG](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — 2026-10-15 — fetched(이전 실행)

### Integrity Technology Group 연계(AA26-281A) — 동남아 정부기관 메일함 대량 복제 및 MicroScan/FishHub 글로벌 봇넷·피싱 인프라 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 1차 출처(AA26-281A, ic3.gov/cisa.gov 전량 세션 네트워크 외부로 재시도 실패) 미확보. 재보도 종합: "actors supported by Integrity Tech use techniques consistent with activity tracked as Flax Typhoon"이며, "techniques overlap with activities publicly tracked as Flax Typhoon, Ethereal Panda, and Red Juliett. However, the agencies note that commercial threat-group labels do not always directly correlate with government attribution"로 서술. "a China-based for-profit company with links to the Chinese government"(재보도 종합, 미검증). PLA/MSS로 승격하지 않음.
- 대상: 동남아시아 정부기관·법집행기관·의료기관·종교단체 M365/Exchange 계정; 미국 사우스캐롤라이나 전력회사, 일본·폴란드 공항, 대만 가스전력 부문도 거론(미검증)
- 초기 침투: 웹 취약점 스캐닝 및 패스워드 스프레이 추정. 정찰 도구 체계(미검증): BBScan, dirsearch, Fscan, ksubdomain, masscan, Nmap, OneForAll, ShuiZe, WPScan
- 주요 도구/멀웨어: MicroScan(IoT 봇넷 기반 스캐너, 미검증), FishHub(피싱 인프라, 미검증)
- 관측 시점: 공동권고(AA26-281A) 공개 2026-10-08
- 출처: 검색 결과만 확인 — AA26-281A(미확보, www.ic3.gov 금일 재시도 미실시), 재보도(전량 EGRESS_BLOCKED 또는 차단 목록 포함 도메인)

### BPFdoor/Rekoobe/AVERAT — 메일보안장비 위장 통신사 침투 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "likely tied to Chinese-linked espionage against telecoms"(재보도, 원문 미검증)
- 대상: 한국·대만 통신사 — SpamSniper·ShareTech 운영사
- 초기 침투: 불명 — 메일보안 게이트웨이 장비에 BPFDoor·Rekoobe 재사용
- 주요 도구/멀웨어: BPFDoor(변종), Rekoobe, AVERAT(신규)
- 관측 시점: 공개 2026-10-05경(추정)
- 출처: 검색 결과만 확인 — Rapid7(차단), 재보도(전량 EGRESS_BLOCKED)

### TA419 — 미국 AI 정책 전문가 대상 자격증명 피싱 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "China-aligned"(재보도, 원문 미검증)
- 대상: 미국 AI 정책 전문가(싱크탱크·대학·법률사무소) 10명 미만
- 초기 침투: AI 정책가·Anthropic 직원 사칭 이메일 → 가짜 OneDrive 로그인 페이지
- 주요 도구/멀웨어: Frameless BitB(브라우저-인-브라우저 피싱 변종)
- 관측 시점: 2026-02·2026-07-08~현재, 공개 2026-10-02경
- 출처: 검색 결과만 확인 — Proofpoint(차단), 재보도(전량 차단)

### UAT-11587 (Antino 백도어) — 아시아 8개국 정부·정책·시민사회 기관 대상 재부상 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "Talos assesses the actor as China-nexus with high confidence"(재보도 종합, 원문 미검증)
- 대상: 대만·인도·필리핀·캄보디아·파키스탄·태국·미얀마·시리아 등 — 약 350개 엔드포인트
- 초기 침투: 대만 학계·시민단체 대상 Gmail 위장 스피어피싱
- 주요 도구/멀웨어: Antino 백도어(Rust), Microsoft Graph API 데드드롭
- 관측 시점: 2025-09~2026-07, 원문 공개 2026-09-30
- 출처: 검색 결과만 확인 — Cisco Talos(차단), 재보도(전량 EGRESS_BLOCKED)

### NeedyMantis — Storm-3069 포스트-컴프로마이즈 악성코드 프레임워크
- 귀속: 귀속 미확인 — "While Microsoft assesses the activity originates from China, it has not attributed Storm-3069 to a Chinese nation-state actor."(Microsoft, 검증)
- 대상: 통신사, 대학, 의료 비영리단체, 국제기구, 정부 계약업체
- 초기 침투: 해당 없음(포스트-컴프로마이즈 전용) — Impacket 기반 핸즈온키보드, DLL 사이드로딩
- 주요 도구/멀웨어: NeedyMantis(모듈형), Impacket
- 관측 시점: 최소 2025-10부터, 2026-09-28 공개
- 출처: [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — 2026-09-28 — fetched(이전 실행)

## 그룹 별칭 매핑
전체 누적 그룹 목록(마지막 관측일 포함)은 [`groups.md`](../groups.md) 참조. 금일 신규 그룹 2건 추가(Crystal Typhoon, Salt Typhoon — 둘 다 Microsoft 2026-11-25 ARTEX 방어자 가이드에서 "ARTEX를 도구체계에 통합"으로만 명명, 구체 캠페인·IOC 없음).

## 악용 CVE (패치 우선순위)
금일 신규 CVE 없음. 전체 누적 목록은 [`exploited-cves.txt`](../exploited-cves.txt) 참조(29건, 검증 13 / 미검증 16).

## C2 도메인 (35, 누적)
신규 없음. 전체 목록은 [`blocklists/domains.txt`](../blocklists/domains.txt) 참조.

## C2 IP (42, 누적)
신규 없음. 전체 목록은 [`blocklists/ips.txt`](../blocklists/ips.txt) 참조.

## 파일 해시 (61, 누적)
신규 없음. 기존 61건은 이전 스냅샷([`snapshots/2026-08-27.md`](2026-08-27.md), [`snapshots/2026-08-28.md`](2026-08-28.md), [`snapshots/2026-09-03.md`](2026-09-03.md), [`snapshots/2026-09-07.md`](2026-09-07.md), [`snapshots/2026-09-25.md`](2026-09-25.md), [`snapshots/2026-10-01.md`](2026-10-01.md), [`snapshots/2026-10-16.md`](2026-10-16.md)) 참조.

## 호스트 IOC · LOTL 아티팩트
신규 없음. 기존 항목은 [`snapshots/2026-09-07.md`](2026-09-07.md), [`snapshots/2026-10-16.md`](2026-10-16.md), [`snapshots/2026-11-03.md`](2026-11-03.md), [`snapshots/2026-11-21.md`](2026-11-21.md) 참조.

## 이번 실행 변경사항
- 신규 캠페인: 없음(기존 10건 유지). Microsoft의 2026-11-25 ARTEX 방어자 가이드는 기존 Storm-0940/ARTEX 캠페인 항목에 대한 보강 정보로 반영(신규 캠페인으로 별도 집계하지 않음)
- 신규 IOC: 없음
- 신규 CVE: 없음
- 제거: 없음(블록리스트·CVE·그룹 파일은 변동 없이 누적 유지)
- 승격(미검증→검증): 없음
- 귀속 변경: 없음
- 신규 그룹: Crystal Typhoon, Salt Typhoon(둘 다 Microsoft 2026-11-25 원문에서 ARTEX 사용 행위자로 명명, 귀속 미확인, 구체 세부사항 없음)
- 7일 창(🔥) 변동: ARMORY CASTLE/vCenter(11-19) 유지 + Storm-0940/ARTEX 방어자 가이드(11-25) 신규 추가
- 비고: WebSearch 8건(지시된 6개 + 추가 보강 검색), WebFetch 8건 수행(성공 4 — Microsoft ARTEX 방어자 가이드(신규, 전체), GTIG AI Threat Tracker(재확인, PentAGI 신규 확인), Microsoft 블로그 색인(재확인), GTIG 블로그 색인(재확인) / 실패 4 — blog.talosintelligence.com, labs.cloudsecurityalliance.org, blog.lumen.com ENOTFOUND, cloud.google.com/.../llmjacking-monetizing-compromised-cloud-models 404(슬러그 오류로 추정, 2차 보도로 날짜만 2026-11-02 확인, 금전적 동기로 서술되어 채택 대상 아님)). APT41/UNC6508의 Cisco SD-WAN(CVE-2026-20245) 연계는 2차 보도에서도 "사이드바 참고링크" 수준으로만 확인되어 미채택.

## 차단 운영 포맷 (복붙용)

### Domain blocklist (un-defanged, one per line)
```
1cv2f3d5s6a9w.ddnsfree.com
admina.freeddns.org
afsaces.accesscam.org
akapush.us.to
applebox.camdvr.org
bggs.giize.com
camcampkes.ddnsfree.com
clients.brendns.workers.dev
closed.theworkpc.com
corp.tripswithengine.com
cpanel.netbar.org
evilginx2.loseyourip.com
googles.accesscam.org
googles.ddnsfree.com
jarzoda.net
jsdelivrs.com
mediareleaseupdates.com
oast.fun
opra1.oprawh.workers.dev
pan.xj.hk
roller.johallow.workers.dev
taiwantradoshows.com
tradostw.com
trcloudflare.com
vmtools.camdvr.org
vmtools.loseyourip.com
wispy.geneva.workers.dev
www.availableextens.com
www.brighyt.com
www.cundis.com
www.decathlonm.com
www.gerikinage.com
www.growhth.com
www.p9-car.com
www.twisinbeth.com
```

### IP blocklist (un-defanged, one per line)
```
101.100.182.122
103.13.28.40
103.147.251.5
103.190.38.3
103.27.110.83
103.73.66.37
103.79.120.72
116.88.34.184
118.174.128.34
118.174.128.36
118.174.128.38
118.189.188.122
129.126.109.50
130.94.6.228
144.172.64.128
144.172.64.60
144.172.64.99
158.140.135.244
166.88.2.90
176.9.89.66
185.71.15.109
187.15.88.186
187.15.89.186
187.15.90.217
193.149.129.191
195.123.211.70
202.59.10.122
206.188.196.199
220.121.128.41
222.108.77.44
223.25.78.136
23.169.65.49
38.180.205.14
38.54.112.184
38.60.171.242
38.60.194.21
45.77.39.28
61.216.56.127
8.218.240.85
8.222.225.8
81.45.89.43
98.142.138.21
```

## 출처
- [Microsoft — What defenders need to know about ARTEX, the agentic AI framework threat actors abuse](https://www.microsoft.com/en-us/security/blog/2026/11/25/what-defenders-need-to-know-artex-agentic-ai-framework-threat-actors-abuse/) — Microsoft — 2026-11-25 — fetched(금일 신규)
- [GTIG AI Threat Tracker: Agentic Threat Activity Crosses a Significant Threshold](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold) — Google GTIG — 2026-11-16 — fetched(금일 재페치, PentAGI 신규 확인)
- [Microsoft Security Blog 메인 색인](https://www.microsoft.com/en-us/security/blog/) — Microsoft — 2026-11-26 조회 — fetched(색인 재확인)
- [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence) — Google GTIG — 2026-11-26 조회 — fetched(색인 재확인)
- [ARMORY CASTLE Exploits vSphere](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere) — Google GTIG — 2026-11-19 — fetched(이전 실행)
- [ARTEX and Friends: Enter Agentic Offensive Frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — Google GTIG/Mandiant — 2026-10-30 — fetched(이전 실행)
- [AI-driven, large-scale nation-state campaign using ARTEX enables supply chain compromise](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — Microsoft — 2026-10-21 — fetched(이전 실행)
- [ARMORY CASTLE Exploits BeyondTrust](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — Google GTIG — 2026-10-15 — fetched(이전 실행)
- [NeedyMantis: Unpacking a post-compromise malware family used in targeted operations](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — Microsoft — 2026-09-28 — fetched(이전 실행)
- [KeyDrift: SD-WAN Controllers as Key-Harvesting Platforms](https://labs.cloudsecurityalliance.org/research/csa-research-note-keydrift-sdwan-key-harvesting-20261030-csa/) — Cloud Security Alliance — 2026-10-30 — blocked(ENOTFOUND)
- [Cisco Talos — UAT-11473/KeyDrift](https://blog.talosintelligence.com/uat-11473-keydrift) — Cisco Talos — 2026-10-28 — blocked(ENOTFOUND)
- [Lumen Black Lotus Labs — Silent Train](https://blog.lumen.com/) — Lumen — 2026-10-28 — blocked(ENOTFOUND)
- [The Rise of LLMJacking](https://cloud.google.com/blog/topics/threat-intelligence/llmjacking-monetizing-compromised-cloud-models) — Google GTIG/Mandiant — 2026-11-02 — fetch 실패(404, 경로 재확인 필요), 2차 보도로 금전적 동기 확인되어 미채택
