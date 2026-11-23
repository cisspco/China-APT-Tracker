# China State APT Campaign Snapshot — 2026-11-23 UTC

## 수집 상태
- 페치 성공: [GTIG AI Threat Tracker: Agentic Threat Activity Crosses a Significant Threshold](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold)(재확인, 신규 PRC-nexus 세부사항 없음, 기존 반영 내용과 일치); [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence)(색인, 최근 11건 확인 — 2026-11-19 ARMORY CASTLE/vSphere 이후 신규 China/PRC-nexus 게시물 없음. COLD RELIC·XCPE Botnet·ShinyHunters·LLMJacking은 기존 실행에서 이미 검토·제외); [Microsoft Security Blog 메인 색인](https://www.microsoft.com/en-us/security/blog/)(색인, 2026-10-19~11-20 게시물 9건 확인 — China/Typhoon/국가 배후 관련 신규 게시물 없음)
- 페치 차단(EGRESS_BLOCKED/DNS 미해석): www.helpnetsecurity.com, cyberscoop.com, www.bleepingcomputer.com, blog.lumen.com, research.checkpoint.com
- 검증된 IOC: 신규 0개(누적 도메인 35·IP 42, 변동 없음) / 미검증 IOC: 신규 0개(누적 도메인 0·IP 0) / 신규 CVE: 0건(누적 29건, 검증 13/미검증 16)

6개 정기 WebSearch 쿼리를 수행했습니다. 그 결과 신규 미검증 캠페인 1건을 추가로 채택했습니다: Check Point Research가 2026-11-10경 공개한 것으로 재보도된 "CopperDragon" 추정 공급자 및 SilentDelivery·OceanGate·DarkWire 3개 클러스터(Sparrow 멀웨어 생태계 기반 코드·인프라 공유). 이 후보는 2026-11-13 실행에서 "후속 검색에서 전혀 재현되지 않아 근거 불충분으로 미채택" 처리되었으나, 금일 재검색에서 Infosecurity Magazine·TheHackerNews·Cybernews 3개 매체가 일관되게 동일 세부사항(클러스터명, 악성코드명, 피해 지역)을 보도하고 있음을 확인하여 재검토·채택했습니다. 1차 출처(research.checkpoint.com)는 이 세션에서 ENOTFOUND로 접근 불가해 전량 미검증으로만 반영했습니다. GTIG·Microsoft 블로그 색인을 직접 재페치해 2026-11-19(ARMORY CASTLE/vSphere) 및 2026-11-20(비China) 이후 신규 China-nexus 포스트가 없음을 재확인했습니다. 그 외 검색에서 발견한 Trellix 활동 동향 보고서(2026-11-04, 중국 국가 배후 활동 41.4% 감소, 특정 그룹·IOC 없는 트렌드 분석)와 FamousSparrow/SparroWocky 관련 재보도(모두 기존 2026-09-17 공개 내용 재인용, 신규 없음)는 기존 처리와 동일하게 미채택/배경 기록만 유지했습니다.

60일 창이 2026-09-24~로 이동했습니다. 기존 13건 캠페인 모두 창 내 유지(Red Heron·Phantom Taurus의 근사 공개일 "2026-09-22경"/"2026-09"는 원문 미확보로 날짜 보정 불가하여 기존 분류 유지). 신규 캠페인 1건(CopperDragon/SilentDelivery·OceanGate·DarkWire) 추가로 총 14건. 7일 창(2026-11-16~2026-11-23) 기준 LEAKY CASTLE/CAIRN(11-16)·ARMORY CASTLE/vCenter(11-19) 2건 🔥(전일 대비 변동 없음), CopperDragon 계열(11-10경)은 7일 창 밖.

## 최근 캠페인 (최근 60일)

### CopperDragon(추정 공급자) / SilentDelivery·OceanGate·DarkWire — Sparrow 생태계 기반 3개 클러스터 공급망 추정 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합: "China-nexus intrusion clusters"(Check Point Research 재보도, Infosecurity Magazine/TheHackerNews/Cybernews, 원문 research.checkpoint.com ENOTFOUND로 미검증). "CopperDragon"은 Check Point가 붙인 추정 공급자 명칭으로, 3개 클러스터와의 관계는 "확인되지 않았다(unconfirmed)"로 서술됨. PLA/MSS 언급 없음.
- 대상: 통신사, 정부기관, 군, 연구기관, critical infrastructure 등 21개국. SilentDelivery는 독일·프랑스·체코의 정상 정부·해운·IT·연구기관 웹사이트를 워터링홀로 활용(재보도 종합)
- 초기 침투: 불명 — 재보도에 구체 벡터·CVE 미기재
- 주요 도구/멀웨어: SquadC, AnnobinDoor, SparrowShell(모두 Windows/Linux, 미공개 신규 멀웨어로 서술) — Sparrow 프레임워크 기반 코드 유사성으로 FamousSparrow(SparroWocky/SparrowDoor)와의 연관성 시사되나 원문 미확보로 동일 그룹 여부 판단 불가
- 관측 시점: 1년여 조사, 공개 2026-11-10경(Check Point)
- 출처: 검색 결과만 확인 — Check Point Research(research.checkpoint.com, ENOTFOUND로 미검증), 재보도([Infosecurity Magazine](https://www.infosecurity-magazine.com/news/chinese-malware-tied-three-hacking/), [TheHackerNews](https://thehackernews.com/2026/11/three-china-nexus-espionage-campaigns.html), [Cybernews](https://cybernews.com/security/new-global-china-cyber-espionage-campaign/) — 전량 EGRESS_BLOCKED/DNS 미해석으로 WebFetch 직접 확인 불가, WebSearch 스니펫만 확보)

### ARMORY CASTLE(구 UNC5221) — VMware vCenter 제로데이(CVE-2026-123890) 추가 익스플로잇, SLIMSAVAGE·BONESAW·LAZYBONES 등 신규 툴셋 🔥
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음. 함께 언급된 UNC6201(BRICKSTORM 관련 TTP 공유)도 "suspected PRC-nexus actor"로만 서술.
- 대상: 불명 — 원문은 "a high-priority environment"로만 서술, 구체 산업·국가 미기재
- 초기 침투: BeyondTrust Remote Support(구 Bomgar) 제로데이 CVE-2026-102764(기존 2026-10-15 공개) 경유 침투 → 내부 Linux 어플라이언스로 측면이동 → VMware vCenter 제로데이 CVE-2026-123890(인증 없는 SRP-6a 세션키 노출, DCE/RPC 2012포트, administrator@vsphere.local 인증우회) 추가 익스플로잇
- 주요 도구/멀웨어: SLIMSAVAGE(JSP 웹셸 `ActiveSer.jsp`, 암호 `pwd=123`), CAGEMATCH(JSP 파일스테이징 웹셸 `u.jsp`), BEARBONES(백도어 Dropbear SSH `/tmp/dbr`, 평문 자격증명 로깅, 배너 `SSH-2.0-pulsesecure_23345`, TCP 53·33992 리슨), BONESAW(Go 익스플로잇 유틸 `/tmp/123`, CVE-2026-123890 익스플로잇), SAWSNAKE(Go SAML 유틸 `/tmp/sss`, Golden SAML 위조), LAZYBONES(Go 백도어 `/usr/bin/vmtoolscs`, Slack API C2, systemd 서비스 50분 주기 재시작·150~450초 지터), vmfs_browser.py(VMFS 볼륨 추출 파이썬 툴, `vmfs-pydist.tar.gz`). 보조 툴: nmap, curl, RAR, WinSCP, gdb
- 관측 시점: BONESAW 실행 2026년 9월 초(CVE-2026-123890 익스플로잇 시점), BONESAW Go 빌드 타임스탬프 2026-07-13T09:21:24Z(변조 가능성 있음), CVE-2026-123890 공개 2026-11-19(VMware·GTIG 동시 공개)
- 출처: [GTIG](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere) — 2026-11-19 — fetched(이전 실행)

### LEAKY CASTLE(PRC 계약업체) 및 CAIRN 프레임워크 — AI/LLM 기반 사이버첩보 활동, 미 항공우주 섹터 표적 🔥
- 귀속: 귀속 미확인 — 원문 인용: "a PRC contractor"(LEAKY CASTLE, GTIG, 검증) / "suspected espionage threat actors with a PRC nexus"·"PRC-nexus cyber espionage actors used LLM tools and models for reconnaissance, front-end scanning, researching targets across various sectors and geographies, and weaponizing exploits"(GTIG, 검증, 2026-11-16). PLA/MSS 명시 없음.
- 대상: LEAKY CASTLE — 원문에 특정 산업·국가 미기재(유출 데이터 분석·번역·이해 목적 LLM 활용으로만 서술). CAIRN 프레임워크 기반 활동 — 미국 항공우주 섹터
- 초기 침투: 불명 — 원문은 LLM을 정찰, 공격표면 스캐닝, 타겟 리서치, 익스플로잇 무기화에 활용한 것으로만 서술하며 구체적 벡터·CVE 미기재
- 주요 도구/멀웨어: CAIRN(공격용 LLM 프레임워크), LEAKY CASTLE(PRC 계약업체 명칭)
- 관측 시점: 2026년 3분기(Q3 2026) 활동, 2026-11-16 GTIG 공개
- 출처: [GTIG AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold) — 2026-11-16 — fetched(재확인)

### Storm-0940(UNC7228) — ARTEX AI 에이전트 기반 ConnectWise 공급망 침해, M365 테넌트 대량 표적화
- 귀속: 귀속 미확인 — 원문 인용: "China-state aligned actor"(Microsoft, 검증) / GTIG 인용: "overlaps with activity tracked by Microsoft as the PRC-nexus actor STORM-0940"(Google GTIG, 검증, 2026-10-30). PLA/MSS 명시 없음.
- 대상: 항공우주·국방, 자동차, 화학, 에너지, 금융서비스, 정부, 법률, 제조, 미디어, 군, 반도체, 소프트웨어, 기술, 싱크탱크·비영리단체 등 전 세계 수백 개 조직. ConnectWise Cloud Backup 멀티테넌트 앱 통해 2,250개 이상 M365 테넌트 대상화.
- 초기 침투: ConnectWise Cloud Backup 멀티테넌트 앱 공급망 침해 → 신뢰된 OAuth 앱 경유 다운스트림 테넌트 접근. 2026-10-10~14(피크 10-11) 패스워드 스프레이. CVE 명시 없음
- 주요 도구/멀웨어: ARTEX(오픈소스 멀티에이전트 LLM 펜테스트 프레임워크, Go+Next.js), 웹셸 `cl1217.jsp` 등, `artex-probe-*` 프로브 패턴
- 관측 시점: 최소 2026-08말부터, 2026-10-10~14 패스워드 스프레이 피크, 2026-10-21 Microsoft 공개, 2026-10-30 GTIG/Mandiant "ARTEX and Friends" 공개(UNC7228 명명)
- 출처: [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — 2026-10-21 — fetched(이전 실행); [GTIG/Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — 2026-10-30 — fetched(이전 실행)

### ARMORY CASTLE(구 UNC5221) — BeyondTrust Remote Support 제로데이 익스플로잇, SAWFLY·BARECLAW
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음.
- 대상: 불명 — 원문에 특정 산업·국가 미기재
- 초기 침투: BeyondTrust Remote Support(구 Bomgar, 26.2.3 이하) 제로데이 CVE-2026-102764(인증 없는 임의 파일 업로드)
- 주요 도구/멀웨어: SAWFLY(PHP 웹셸 `mangoapi.php`), BARECLAW(SOCKS5-over-WebSocket 터널러 `ingredi_ws`)
- 관측 시점: 제로데이 익스플로잇 2026년 8월 말, 2026-10-15 공개
- 출처: [GTIG](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — 2026-10-15 — fetched(이전 실행)

### Integrity Technology Group 연계(AA26-281A) — 동남아 정부기관 메일함 대량 복제 및 MicroScan/FishHub 글로벌 봇넷·피싱 인프라 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 1차 출처(AA26-281A, FBI/CISA/NSA/NCSC-UK 공동권고, ic3.gov·cyber.gov.au 전량 EGRESS_BLOCKED로 미확보) 미확보, 재보도만 확인. Integrity Technology Group은 과거 미 재무부(OFAC)가 Flax Typhoon 인프라 제공 혐의로 제재한 중국 기업. 재보도: "actors supported by Integrity Tech use techniques consistent with activity tracked as Flax Typhoon", "a China-based for-profit company with links to the Chinese government"(재보도 종합, 미검증). PLA/MSS로 승격하지 않음.
- 대상: 동남아시아 정부기관·법집행기관·의료기관·종교단체 M365/Exchange 계정; 미국 사우스캐롤라이나 전력회사, 일본·폴란드 공항, 대만 가스전력 부문도 피해 대상 거론(재보도, 미검증)
- 초기 침투: 웹 취약점 스캐닝 및 패스워드 스프레이 추정
- 주요 도구/멀웨어: MicroScan(IoT 봇넷 기반 스캐너, 미검증), FishHub(피싱 인프라, 미검증)
- 관측 시점: 공동권고(AA26-281A) 공개 2026-10-08
- 출처: 검색 결과만 확인 — AA26-281A(1차 출처 미확보), 재보도(전량 EGRESS_BLOCKED)

### UAT-11473(KeyDrift) — Cisco SD-WAN 제로데이, Volt Typhoon "Silent Train" 인프라 중첩 ⚠️ (미검증)
- 귀속: 귀속 미확인 — Talos 원문(재보도 종합)은 UAT-11473 자체에 국가 귀속 표현을 직접 사용하지 않음. "infrastructure overlaps considerably with Volt Typhoon's 'Silent Train'"로만 서술하며 두 행위자를 동일시하지 않음(재보도 종합, 원문 미확보). PLA/MSS 언급 없음.
- 대상: 우주·위성 서비스, 국방·항공우주 기술, 정책 연구기관(피해 국가·조직명 재보도에 미기재)
- 초기 침투: CVE-2026-20127(Cisco Catalyst SD-WAN Controller, vSmart/vBond 인증 우회, CVSS 10.0)
- 주요 도구/멀웨어: KeyDrift 프레임워크 — PolyFlame(메모리 상주 모듈, `libdssl.so`), LittleFilch(OpenSSL `SSL_read` 후킹 AES-256 키 자재 추출 모듈)
- 관측 시점: 활동은 "historical"로만 서술, 공개 2026-10-28(Cisco Talos)
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

### Phantom Taurus — NET-STAR IIS 멀웨어 스위트 정부·통신사 첩보 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "espionage operations align with the strategic interests of the People's Republic of China (PRC)"(재보도, 원문 미검증)
- 대상: 아프리카·중동·아시아 정부기관(외교부, 대사관) 및 통신사
- 초기 침투: 불명 — IIS 웹서버 거점 활용
- 주요 도구/멀웨어: NET-STAR(.NET, IIS 워커 프로세스 w3wp.exe 메모리 상주)
- 관측 시점: 계보 2023-06~2024-05~현재, 공개 2026-09(정확한 날짜 미확보)
- 출처: 검색 스니펫만 확인 — Unit 42(지속 차단)

### Red Heron — WordPress·Zyxel·Ubiquiti·Gitea 연쇄 익스플로잇 정부기관 데이터 탈취 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "Chinese-speaking threat actor linked to the Red Heron group"(재보도, 원문 미검증)
- 대상: 정부·법집행기관 등 49개 조직(29개국), Zyxel GS1900 스위치 996대(48개국)
- 초기 침투: WordPress wp2shell(CVE-2026-63030/60137), Zyxel GS1900(CVE-2026-7273), Ubiquiti UniFi(CVE-2026-34908/34909/34910), Gitea(CVE-2026-60004)
- 주요 도구/멀웨어: 신원 미상 Linux 루트킷, AMSI 우회
- 관측 시점: 최소 2026-06초부터, 공개 2026-09-22경
- 출처: 검색 스니펫만 확인 — Acronis TRU(차단), GreyNoise(차단)

### VAPOR PANDA — ARTEX/DeepSeek AI 에이전트 기반 글로벌 동시다발 침투 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "China-based targeted intrusion adversary"(CrowdStrike, 재보도 종합, 원문 미검증), 구 VexatiousTemper(2021년부터 추적)
- 대상: 정부부처, 통신사(미국·벨기에·필리핀), 제약·반도체·국방·원자력·금융 등 14개국 200개 이상 조직
- 초기 침투: 불명 — ARTEX를 DeepSeek 등으로 구동한 자동화된 정찰·침투(재보도)
- 주요 도구/멀웨어: ARTEX, BLOODALCHEMY 백도어
- 관측 시점: 캠페인 2026-10-17~10-28, 공개 2026-10-29~30
- 출처: 검색 결과만 확인 — CrowdStrike(DNS 미해석), 재보도(다수)

## 그룹 별칭 매핑
전체 누적 그룹 목록(마지막 관측일 포함)은 [`groups.md`](../groups.md) 참조. 금일 신규 그룹 1건 추가(CopperDragon(추정 공급자)/SilentDelivery·OceanGate·DarkWire, 미검증).

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
- 신규 캠페인: 1건(CopperDragon(추정 공급자)/SilentDelivery·OceanGate·DarkWire, 미검증 — 2026-11-13 실행에서 "근거 불충분으로 미채택" 처리되었으나 금일 3개 매체 일관 보도 확인으로 재검토·채택)
- 신규 IOC: 없음(구체 도메인/IP/해시 값은 재보도에 미제시)
- 신규 CVE: 없음
- 제거: 없음
- 캠페인 목록 변동: 13건 → 14건(CopperDragon 계열 추가)
- 승격(미검증→검증): 없음
- 귀속 변경: 없음
- 그룹 메타데이터 갱신: 신규 그룹 1건 추가(CopperDragon/SilentDelivery·OceanGate·DarkWire)
- 비고: WebFetch 8건 수행(성공 3 — GTIG AI Threat Tracker 재확인, GTIG 블로그 색인, Microsoft 블로그 색인 / 실패 5 — www.helpnetsecurity.com, cyberscoop.com, www.bleepingcomputer.com, blog.lumen.com, research.checkpoint.com 전부 ENOTFOUND). GTIG·Microsoft 양쪽 색인 모두 2026-11-19/11-20 이후 신규 China-nexus 콘텐츠 없음을 확인.

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
- [Suspected Chinese Malware Supplier Tied to Three Hacking Campaigns](https://www.infosecurity-magazine.com/news/chinese-malware-tied-three-hacking/) — Infosecurity Magazine(Check Point Research 재인용) — 2026-11-10경 — blocked(원문 research.checkpoint.com ENOTFOUND, 재보도만 확인)
- [Three China-Nexus Espionage Campaigns](https://thehackernews.com/2026/11/three-china-nexus-espionage-campaigns.html) — TheHackerNews — 2026-11경 — blocked(EGRESS_BLOCKED)
- [Chinese spies are hacking the services you rely on](https://cybernews.com/security/new-global-china-cyber-espionage-campaign/) — Cybernews — 2026-11경 — blocked(EGRESS_BLOCKED)
- [ARMORY CASTLE Exploits vSphere](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere) — Google GTIG — 2026-11-19 — fetched(이전 실행)
- [GTIG AI Threat Tracker: Agentic Threat Activity Crosses a Significant Threshold](https://cloud.google.com/blog/topics/threat-intelligence/agentic-threat-activity-crosses-a-significant-threshold) — Google GTIG — 2026-11-16 — fetched(재확인)
- [ARTEX and Friends: Enter Agentic Offensive Frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — Google GTIG/Mandiant — 2026-10-30 — fetched(이전 실행)
- [AI-driven, large-scale nation-state campaign using ARTEX enables supply chain compromise](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — Microsoft — 2026-10-21 — fetched(이전 실행)
- [ARMORY CASTLE Exploits BeyondTrust](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — Google GTIG — 2026-10-15 — fetched(이전 실행)
- [NeedyMantis: Unpacking a post-compromise malware family used in targeted operations](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — Microsoft — 2026-09-28 — fetched(이전 실행)
- [Chinese Government-linked Cyber Threat Actors Combine Automated and Hands-on Hacking Tools to Steal Sensitive Data (AA26-281A)](https://www.cisa.gov/) — FBI/CISA/NSA/NCSC-UK — 2026-10-08 — blocked(EGRESS_BLOCKED, 재보도 종합으로만 반영)
- [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence) — Google GTIG — 2026-11-23 조회 — fetched(색인, 신규 China-nexus 게시물 없음)
- [Microsoft Security Blog 메인 색인](https://www.microsoft.com/en-us/security/blog/) — Microsoft — 2026-11-23 조회 — fetched(색인, 신규 China-nexus 게시물 없음)
