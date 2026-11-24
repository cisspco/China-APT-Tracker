# China State APT Campaign Snapshot — 2026-11-24 UTC

## 수집 상태
- 페치 성공: [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence)(색인 재확인 — 2026-11-19 ARMORY CASTLE/vSphere 이후 신규 China/PRC-nexus 게시물 없음. 상위 11건 모두 기존 실행에서 이미 검토·반영 또는 제외된 항목); [Microsoft Security Blog 메인 색인](https://www.microsoft.com/en-us/security/blog/)(색인 재확인 — 2026-11-17 이후 신규 게시물 3건 확인, 모두 China/Typhoon/국가배후 비관련: "Microsoft named a Leader in the 2026 Gartner® Magic Quadrant™ for SIEM"(11-20), "Security for the agentic era, powered by Microsoft Perception"(11-17), "The risks of device code authentication for AI coding agents"(11-17))
- 페치 차단(EGRESS_BLOCKED/ENOTFOUND): securelist.com(Kaspersky, PassiveNeuron 캠페인 원문), www.nextgov.com(Volt Typhoon 신규 인프라 재보도), www.govinfosecurity.com(Volt Typhoon "Silent Train" 재보도), www.recordedfuture.com(RedNovember 보고서), www.darktrace.com(Royal Thai Police 캠페인 재보도), www.cyfirma.com(China 위협 인텔리전스 리포트)
- 검증된 IOC: 신규 0개(누적 도메인 35·IP 42, 변동 없음) / 미검증 IOC: 신규 0개(누적 도메인 0·IP 0) / 신규 CVE: 0건(누적 29건, 검증 13/미검증 16)

6개 정기 WebSearch 쿼리를 수행했습니다. 신규로 포착된 후보는 다음과 같으나 전부 1차 출처 미확보 또는 귀속·날짜 불충분으로 미채택했습니다: (1) Kaspersky GReAT "PassiveNeuron" 캠페인(Neursite C++ 백도어, NeuralExecutor .NET 임플란트, Cobalt Strike 병용, 정부·금융·산업 섹터, 아시아·아프리카·라틴아메리카 대상) — 귀속이 "likely associated with a Chinese-speaking threat actor"(low confidence, 일부 아티팩트는 분석 혼선용 false flag 가능성 있다고 Kaspersky 자신이 명시)로 극히 낮은 확신도이며 원문(securelist.com) ENOTFOUND로 미확보, 정확한 보고서 공개일도 검색 스니펫에서 확인 불가해 미채택. (2) Black Lotus Labs(Lumen)의 Volt Typhoon "Silent Train" 커버트 릴레이 네트워크 원 보고서(2026-10-28/29 공개 추정) — UAT-11473/KeyDrift 캠페인(2026-10-28, 기존 등재)과의 인프라 중첩만 이미 반영되어 있고, Volt Typhoon 자체를 주체로 한 이 원 보고서는 1차 출처(blog.lumen.com) 및 재보도(thehackernews, cyberscoop, bleepingcomputer, helpnetsecurity, bankinfosecurity/govinfosecurity) 전량 접근 불가로 신규 캠페인으로 분리 등재하지 않음. (3) RedNovember(Recorded Future) — 정부·국방·기술 섹터 대상, 인터넷 노출 장비 취약점 악용으로 초기접근 확보하는 것으로 재보도되나, 검색 스니펫에 중국 국가배후 귀속 표현이 전혀 없어(China/PRC 언급 없음) 채택 기준 미충족. (4) Darktrace "Chinese APT target Royal Thai Police" — 제목상 중국 APT 귀속을 시사하나 원문(darktrace.com) ENOTFOUND, 공개일도 미확인되어 60일 창 내 여부 판단 불가, 미채택. (5) APT41/UNC6508의 유럽·아시아 해운·물류·자동차 섹터 침투(Mandiant 재보도) — 기존 등재된 UNC6508(최종 관측 2026-09-20) 캠페인과 동일 클러스터로 추정되나 날짜·세부사항이 기존 반영 내용과 구분되지 않아 신규 항목으로 분리하지 않음.

60일 창이 2026-09-25~로 이동했습니다. 기존 14건 캠페인 중 Red Heron(공개 "2026-09-22경")은 근사 공개일 기준 창 밖으로 이동했으나, 정확한 날짜가 끝내 확보되지 않아(원문 acronis.com/greynoise.io 전량 EGRESS_BLOCKED 지속) 수일 전부터 이어진 보정 불가 상태를 고려해 이번 실행까지만 유지하고 차기 실행부터는 창 밖으로 제외할 예정임을 기록합니다. Phantom Taurus(공개 "2026-09", 정확한 일자 미확보)도 동일 사유로 금일까지 유지합니다. 그 외 12건은 모두 창 내 명확히 유지. 신규 캠페인 없이 총 14건 유지. 7일 창(2026-11-17~2026-11-24) 기준 ARMORY CASTLE/vCenter(11-19)만 🔥 유지, LEAKY CASTLE/CAIRN(11-16)은 7일 창을 벗어나 🔥 해제.

## 최근 캠페인 (최근 60일)

### ARMORY CASTLE(구 UNC5221) — VMware vCenter 제로데이(CVE-2026-123890) 추가 익스플로잇, SLIMSAVAGE·BONESAW·LAZYBONES 등 신규 툴셋 🔥
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음.
- 대상: 불명 — 원문은 "a high-priority environment"로만 서술, 구체 산업·국가 미기재
- 초기 침투: BeyondTrust Remote Support(구 Bomgar) 제로데이 CVE-2026-102764(기존 2026-10-15 공개) 경유 침투 → 내부 Linux 어플라이언스로 측면이동 → VMware vCenter 제로데이 CVE-2026-123890(인증 없는 SRP-6a 세션키 노출, DCE/RPC 2012포트, administrator@vsphere.local 인증우회) 추가 익스플로잇
- 주요 도구/멀웨어: SLIMSAVAGE(JSP 웹셸 `ActiveSer.jsp`), CAGEMATCH(JSP 파일스테이징 웹셸 `u.jsp`), BEARBONES(백도어 Dropbear SSH `/tmp/dbr`, TCP 53·33992 리슨), BONESAW(Go 익스플로잇 유틸 `/tmp/123`), SAWSNAKE(Go SAML 유틸 `/tmp/sss`, Golden SAML 위조), LAZYBONES(Go 백도어 `/usr/bin/vmtoolscs`, Slack API C2), vmfs_browser.py(VMFS 볼륨 추출)
- 관측 시점: BONESAW 실행 2026년 9월 초, CVE-2026-123890 공개 2026-11-19
- 출처: [GTIG](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere) — 2026-11-19 — fetched(이전 실행)

### LEAKY CASTLE(PRC 계약업체) 및 CAIRN 프레임워크 — AI/LLM 기반 사이버첩보 활동, 미 항공우주 섹터 표적
- 귀속: 귀속 미확인 — 원문 인용: "a PRC contractor"(LEAKY CASTLE, GTIG, 검증) / "PRC-nexus cyber espionage actors used LLM tools and models for reconnaissance, front-end scanning, researching targets across various sectors and geographies, and weaponizing exploits"(GTIG, 검증). PLA/MSS 명시 없음.
- 대상: LEAKY CASTLE — 원문에 특정 산업·국가 미기재. CAIRN 프레임워크 기반 활동 — 미국 항공우주 섹터
- 초기 침투: 불명 — LLM을 정찰, 공격표면 스캐닝, 타겟 리서치, 익스플로잇 무기화에 활용한 것으로만 서술
- 주요 도구/멀웨어: CAIRN(공격용 LLM 프레임워크), LEAKY CASTLE(PRC 계약업체 명칭)
- 관측 시점: 2026년 3분기(Q3 2026) 활동, 2026-11-16 GTIG 공개
- 출처: [GTIG AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold) — 2026-11-16 — fetched(이전 실행)

### Storm-0940(UNC7228) — ARTEX AI 에이전트 기반 ConnectWise 공급망 침해, M365 테넌트 대량 표적화
- 귀속: 귀속 미확인 — 원문 인용: "China-state aligned actor"(Microsoft, 검증) / "PRC-nexus actor STORM-0940"(GTIG 인용, 검증). PLA/MSS 명시 없음.
- 대상: 항공우주·국방, 자동차, 화학, 에너지, 금융서비스, 정부, 법률, 제조, 미디어, 군, 반도체, 소프트웨어, 기술, 싱크탱크·비영리단체 등 전 세계 수백 개 조직. ConnectWise Cloud Backup 멀티테넌트 앱 통해 2,250개 이상 M365 테넌트 대상화.
- 초기 침투: ConnectWise Cloud Backup 멀티테넌트 앱 공급망 침해 → 신뢰된 OAuth 앱 경유. 2026-10-10~14 패스워드 스프레이. CVE 명시 없음
- 주요 도구/멀웨어: ARTEX(오픈소스 멀티에이전트 LLM 펜테스트 프레임워크, Go+Next.js), 웹셸 `cl1217.jsp` 등
- 관측 시점: 최소 2026-08말부터, 2026-10-21 Microsoft 공개, 2026-10-30 GTIG/Mandiant 보강 공개
- 출처: [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — 2026-10-21 — fetched(이전 실행); [GTIG/Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — 2026-10-30 — fetched(이전 실행)

### ARMORY CASTLE(구 UNC5221) — BeyondTrust Remote Support 제로데이 익스플로잇, SAWFLY·BARECLAW
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음.
- 대상: 불명 — 원문에 특정 산업·국가 미기재
- 초기 침투: BeyondTrust Remote Support(구 Bomgar, 26.2.3 이하) 제로데이 CVE-2026-102764(인증 없는 임의 파일 업로드)
- 주요 도구/멀웨어: SAWFLY(PHP 웹셸 `mangoapi.php`), BARECLAW(SOCKS5-over-WebSocket 터널러 `ingredi_ws`)
- 관측 시점: 제로데이 익스플로잇 2026년 8월 말, 2026-10-15 공개
- 출처: [GTIG](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — 2026-10-15 — fetched(이전 실행)

### CopperDragon(추정 공급자) / SilentDelivery·OceanGate·DarkWire — Sparrow 생태계 기반 3개 클러스터 공급망 추정 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합: "China-nexus intrusion clusters"(Check Point Research 재보도, 원문 research.checkpoint.com 미확보). "CopperDragon"은 Check Point 추정 공급자 명칭이며 3개 클러스터와의 관계는 "unconfirmed"로 서술됨. PLA/MSS 언급 없음.
- 대상: 통신사, 정부기관, 군, 연구기관, critical infrastructure 등 21개국
- 초기 침투: 불명 — 재보도에 구체 벡터·CVE 미기재
- 주요 도구/멀웨어: SquadC, AnnobinDoor, SparrowShell — Sparrow 프레임워크 기반 코드 유사성으로 FamousSparrow와의 연관성 시사되나 원문 미확보
- 관측 시점: 1년여 조사, 공개 2026-11-10경(Check Point)
- 출처: 검색 결과만 확인 — Check Point Research(미확보), 재보도([Infosecurity Magazine](https://www.infosecurity-magazine.com/news/chinese-malware-tied-three-hacking/), [TheHackerNews](https://thehackernews.com/2026/11/three-china-nexus-espionage-campaigns.html), [Cybernews](https://cybernews.com/security/new-global-china-cyber-espionage-campaign/))

### Integrity Technology Group 연계(AA26-281A) — 동남아 정부기관 메일함 대량 복제 및 MicroScan/FishHub 글로벌 봇넷·피싱 인프라 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 1차 출처(AA26-281A) 미확보. 재보도: "actors supported by Integrity Tech use techniques consistent with activity tracked as Flax Typhoon", "a China-based for-profit company with links to the Chinese government"(재보도 종합, 미검증). PLA/MSS로 승격하지 않음.
- 대상: 동남아시아 정부기관·법집행기관·의료기관·종교단체 M365/Exchange 계정; 미국 사우스캐롤라이나 전력회사, 일본·폴란드 공항, 대만 가스전력 부문도 거론(미검증)
- 초기 침투: 웹 취약점 스캐닝 및 패스워드 스프레이 추정
- 주요 도구/멀웨어: MicroScan(IoT 봇넷 기반 스캐너, 미검증), FishHub(피싱 인프라, 미검증)
- 관측 시점: 공동권고(AA26-281A) 공개 2026-10-08
- 출처: 검색 결과만 확인 — AA26-281A(미확보), 재보도(전량 EGRESS_BLOCKED)

### UAT-11473(KeyDrift) — Cisco SD-WAN 제로데이, Volt Typhoon "Silent Train" 인프라 중첩 ⚠️ (미검증)
- 귀속: 귀속 미확인 — Talos 원문(재보도 종합)은 UAT-11473 자체에 국가 귀속 표현을 직접 사용하지 않음. "infrastructure overlaps considerably with Volt Typhoon's 'Silent Train'"로만 서술. PLA/MSS 언급 없음.
- 대상: 우주·위성 서비스, 국방·항공우주 기술, 정책 연구기관
- 초기 침투: CVE-2026-20127(Cisco Catalyst SD-WAN Controller, vSmart/vBond 인증 우회, CVSS 10.0)
- 주요 도구/멀웨어: KeyDrift 프레임워크 — PolyFlame(`libdssl.so`), LittleFilch(OpenSSL `SSL_read` 후킹)
- 관측 시점: 활동 "historical", 공개 2026-10-28(Cisco Talos)
- 출처: 검색 결과만 확인 — Cisco Talos(차단), 재보도(일부 차단)

### UAT-11587 (Antino 백도어) — 아시아 8개국 정부·정책·시민사회 기관 대상 재부상 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "Talos assesses the actor as China-nexus with high confidence"(재보도 종합, 원문 미검증)
- 대상: 대만·인도·필리핀·캄보디아·파키스탄·태국·미얀마·시리아 등 — 약 350개 엔드포인트
- 초기 침투: 대만 학계·시민단체 대상 Gmail 위장 스피어피싱
- 주요 도구/멀웨어: Antino 백도어(Rust), Microsoft Graph API 데드드롭
- 관측 시점: 2025-09~2026-07, 원문 공개 2026-09-30
- 출처: 검색 결과만 확인 — Cisco Talos(차단), 재보도(전량 EGRESS_BLOCKED)

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

### NeedyMantis — Storm-3069 포스트-컴프로마이즈 악성코드 프레임워크
- 귀속: 귀속 미확인 — "While Microsoft assesses the activity originates from China, it has not attributed Storm-3069 to a Chinese nation-state actor."(Microsoft, 검증)
- 대상: 통신사, 대학, 의료 비영리단체, 국제기구, 정부 계약업체
- 초기 침투: 해당 없음(포스트-컴프로마이즈 전용) — Impacket 기반 핸즈온키보드, DLL 사이드로딩
- 주요 도구/멀웨어: NeedyMantis(모듈형), Impacket
- 관측 시점: 최소 2025-10부터, 2026-09-28 공개
- 출처: [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — 2026-09-28 — fetched(이전 실행)

### Phantom Taurus — NET-STAR IIS 멀웨어 스위트 정부·통신사 첩보 캠페인 ⚠️ (미검증, 공개일 미확보 — 60일 창 경계 인접)
- 귀속: 귀속 미확인 — "espionage operations align with the strategic interests of the People's Republic of China (PRC)"(재보도, 원문 미검증)
- 대상: 아프리카·중동·아시아 정부기관(외교부, 대사관) 및 통신사
- 초기 침투: 불명 — IIS 웹서버 거점 활용
- 주요 도구/멀웨어: NET-STAR(.NET, IIS 워커 프로세스 w3wp.exe 메모리 상주)
- 관측 시점: 계보 2023-06~2024-05~현재, 공개 2026-09(정확한 날짜 미확보)
- 출처: 검색 스니펫만 확인 — Unit 42(지속 차단)

### Red Heron — WordPress·Zyxel·Ubiquiti·Gitea 연쇄 익스플로잇 정부기관 데이터 탈취 ⚠️ (미검증, 60일 창 경계 — 차기 실행부터 제외 예정)
- 귀속: 귀속 미확인 — "Chinese-speaking threat actor linked to the Red Heron group"(재보도, 원문 미검증)
- 대상: 정부·법집행기관 등 49개 조직(29개국), Zyxel GS1900 스위치 996대(48개국)
- 초기 침투: WordPress wp2shell(CVE-2026-63030/60137), Zyxel GS1900(CVE-2026-7273), Ubiquiti UniFi(CVE-2026-34908/34909/34910), Gitea(CVE-2026-60004)
- 주요 도구/멀웨어: 신원 미상 Linux 루트킷, AMSI 우회
- 관측 시점: 최소 2026-06초부터, 공개 2026-09-22경(60일 창 밖으로 추정되나 정확한 날짜 미확보로 금일까지만 유지)
- 출처: 검색 스니펫만 확인 — Acronis TRU(차단), GreyNoise(차단)

### VAPOR PANDA — ARTEX/DeepSeek AI 에이전트 기반 글로벌 동시다발 침투 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "China-based targeted intrusion adversary"(CrowdStrike, 재보도 종합, 원문 미검증), 구 VexatiousTemper
- 대상: 정부부처, 통신사(미국·벨기에·필리핀), 제약·반도체·국방·원자력·금융 등 14개국 200개 이상 조직
- 초기 침투: 불명 — ARTEX를 DeepSeek 등으로 구동한 자동화된 정찰·침투(재보도)
- 주요 도구/멀웨어: ARTEX, BLOODALCHEMY 백도어
- 관측 시점: 캠페인 2026-10-17~10-28, 공개 2026-10-29~30
- 출처: 검색 결과만 확인 — CrowdStrike(DNS 미해석), 재보도(다수)

## 그룹 별칭 매핑
전체 누적 그룹 목록(마지막 관측일 포함)은 [`groups.md`](../groups.md) 참조. 금일 신규 그룹 없음.

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
- 신규 캠페인: 없음
- 신규 IOC: 없음
- 신규 CVE: 없음
- 제거: 없음
- 캠페인 목록 변동: 14건 유지(신규 없음). Red Heron은 근사 공개일 기준 60일 창 경계를 넘었으나 정확한 날짜 미확보로 금일까지만 유지, 차기 실행부터 "최근 캠페인" 절에서 제외 예정(그룹·IOC는 누적 유지)
- 승격(미검증→검증): 없음
- 귀속 변경: 없음
- 7일 창(🔥) 변동: LEAKY CASTLE/CAIRN(11-16)이 7일 창을 벗어나 🔥 해제, ARMORY CASTLE/vCenter(11-19)만 🔥 유지
- 비고: WebFetch 8건 수행(성공 2 — GTIG 블로그 색인, Microsoft 블로그 색인 재확인 / 실패 6 — securelist.com, www.nextgov.com, www.govinfosecurity.com, www.recordedfuture.com, www.darktrace.com, www.cyfirma.com 전부 ENOTFOUND). 검토 후 미채택한 신규 후보 5건(PassiveNeuron, Silent Train 원보고서, RedNovember, Royal Thai Police 캠페인, APT41/UNC6508 해운 섹터 재보도)은 수집 상태 절에 사유 기록.

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
- [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence) — Google GTIG — 2026-11-24 조회 — fetched(색인, 신규 China-nexus 게시물 없음)
- [Microsoft Security Blog 메인 색인](https://www.microsoft.com/en-us/security/blog/) — Microsoft — 2026-11-24 조회 — fetched(색인, 신규 게시물 3건 모두 China 비관련)
- [ARMORY CASTLE Exploits vSphere](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere) — Google GTIG — 2026-11-19 — fetched(이전 실행)
- [GTIG AI Threat Tracker: Agentic Threat Activity Crosses a Significant Threshold](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold) — Google GTIG — 2026-11-16 — fetched(이전 실행)
- [ARTEX and Friends: Enter Agentic Offensive Frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — Google GTIG/Mandiant — 2026-10-30 — fetched(이전 실행)
- [AI-driven, large-scale nation-state campaign using ARTEX enables supply chain compromise](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — Microsoft — 2026-10-21 — fetched(이전 실행)
- [ARMORY CASTLE Exploits BeyondTrust](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — Google GTIG — 2026-10-15 — fetched(이전 실행)
- [NeedyMantis: Unpacking a post-compromise malware family used in targeted operations](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — Microsoft — 2026-09-28 — fetched(이전 실행)
- [PassiveNeuron campaign with APT implants and Cobalt Strike](https://securelist.com/passiveneuron-campaign-with-apt-implants-and-cobalt-strike/117745/) — Kaspersky GReAT — 날짜 미확보 — blocked(ENOTFOUND, 검토 후 미채택)
- [China's 'Volt Typhoon' quietly built another hacking network following US crackdown, new findings say](https://www.nextgov.com/cybersecurity/2026/10/chinas-volt-typhoon-quietly-built-another-hacking-network-following-us-crackdown-new-findings-say/416848/) — Nextgov — 2026-10 — blocked(ENOTFOUND, 검토 후 미채택)
- [Exposed: Volt Typhoon's Framework for Silent Espionage](https://www.govinfosecurity.com/exposed-volt-typhoons-framework-for-silent-espionage-a-33305) — GovInfoSecurity — 2026-10경 — blocked(ENOTFOUND, 검토 후 미채택)
- [RedNovember Targets Government, Defense, and Technology Organizations](https://www.recordedfuture.com/research/rednovember-targets-government-defense-and-technology-organizations) — Recorded Future — 날짜 미확보 — blocked(ENOTFOUND, 중국 귀속 표현 검색 스니펫에 없어 미채택)
- [Chinese APT target Royal Thai Police in malware campaign](https://www.darktrace.com/fr/blog/chinese-apt-target-royal-thai-police-in-malware-campaign) — Darktrace — 날짜 미확보 — blocked(ENOTFOUND, 검토 후 미채택)
- [China Cybersecurity Threat Intelligence Report](https://www.cyfirma.com/research/china-cybersecurity-threat-intelligence-report) — Cyfirma — 날짜 미확보 — blocked(ENOTFOUND)
