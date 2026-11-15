# China State APT Campaign Snapshot — 2026-11-15 UTC

## 수집 상태
- 페치 성공: [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence)(GTIG/Mandiant, 색인 페이지만); [Defending Against Active Exploitation of Citrix NetScaler ADC and Gateway Appliances](https://cloud.google.com/blog/topics/threat-intelligence/defending-against-active-exploitation-of-citrix-netscaler-adc-and-gateway-appliances/)(Mandiant/GTIG, 본문 — 귀속 없음, 미채택); [Microsoft Security Blog 색인](https://www.microsoft.com/en-us/security/blog/)(Microsoft, 색인 페이지만)
- 페치 차단(EGRESS_BLOCKED): 없음(오늘 시도한 1차 출처 전량 성공 — 단, 다수 WebSearch 결과의 1차 출처(acronis.com, greynoise.io, talosintelligence.com, unit42.paloaltonetworks.com, proofpoint.com 등)는 과거 실행에서 이미 차단 확인된 상태로 재시도하지 않음)
- 검증된 IOC: 신규 0개(누적 도메인 35·IP 31·해시 61) / 미검증 IOC: 신규 0개(누적 도메인 0·IP 0) / 신규 CVE: 0건(누적 27, 검증 12/미검증 15)

6개 정기 WebSearch 쿼리(중국 국가 배후 APT IOC, Typhoon 계열, APT31/40/41, Mustang Panda/i-Soon/Chengdu 404, CISA PRC 권고, PLA 전략지원부대)와 GTIG(`site:cloud.google.com`)·Microsoft(`site:microsoft.com`) 타겟 검색, 그리고 당일(2026-11-15) 기준 최신성 검색(지난 24~48시간 포커스)을 추가로 수행했습니다. GTIG·Microsoft 양측 블로그 색인을 직접 페치해 확인한 결과, 2026-11-14 이후 신규로 게시된 중국 국가 배후 귀속 캠페인은 없었습니다(GTIG 최신 글: LLMJacking·XCPE 봇넷·Vulnerability Discovery AI Era·Citrix NetScaler·BREEZE COMET 등 — 전부 비중국 귀속 또는 범죄 활동; Microsoft 최신 글: SCKit/ScreenConnect, GSocket C2, AI 코딩 에이전트 공급망 공격 등 — 중국 귀속 언급 없음). 검색 결과 대부분은 60일 창(2026-09-17~) 밖의 과거 자료(RedNovember — 2025-09; GRIDTIDE/UNC2814 — 2026-02-25; AA26-113A 공동권고 — 2026-04-23; Trellix 반기 보고서 — 2026-11-04, 신규 IOC 없는 통계성 자료) 또는 기존 반영 캠페인(Storm-0940/ARTEX, ARMORY CASTLE, UAT-11587/Antino, TA419, Mustang Panda/Twill Typhoon 등)의 재보도였습니다.

금일 신규 후보로 검토했으나 **미채택**한 항목:
- **Citrix NetScaler ADC/Gateway 제로데이 캠페인(WHIPSHOT·SLAPSHOT)**(Mandiant/GTIG, 2026-09-29 공개, 1차 출처 본문 직접 확보·검증): CVE-2026-88772(사전인증 제로데이, 힙 메모리 손상)·CVE-2026-88771(미인증 RCE) 악용, WHIPSHOT(PHP 웹셸/터널러)·SLAPSHOT(Python TCP 터널러) 배포, 정부·금융·기술·교육·법률 분야(북미·유럽) 표적. **본문에 "China", "PRC", "UNC", "APT" 등 귀속 표현이 전혀 없음** — "the threat actor"로만 기술. 일부 2차 매체(SC Media/SC World)가 "china backed hackers suspected"로 보도했으나 1차 출처(GTIG/Mandiant)가 직접 확보·검증된 본문에서 그런 귀속을 전혀 하지 않았으므로, 본 리포트의 귀속 원칙("1차 출처가 명시적으로 밝힌 경우만 채택")에 따라 미채택. 특정 CVE(CVE-2026-88771/88772)를 `exploited-cves.txt`에 "Unattributed"로 추가하지 않은 이유: 현재 정책상 그룹/귀속 없는 일반 미귀속 취약점은 CVE 목록에 포함하지 않음(CVE-2026-59310 vCenter 사례만 "Chinese-speaking, moderate confidence" 서술이 있어 예외적으로 포함됨 — 본 Citrix 사례는 그런 서술조차 1차 출처에 없음).
- **Vulnerability Discovery and Exploitation Trends in the AI Era**(GTIG, 2026-09-30 공개): AI 활용 취약점 발견·악용 통계 보고서. PRC/DPRK 등 특정 국가 귀속 언급 없이 전반적 트렌드만 서술 — 미채택.
- **Trellix 반기 위협 보고서(2026-11-04)**: "Chinese nation-state threat activity fell 41.4%"라는 통계와 Mustang Panda 탐지 비율(7.52%)만 제시 — 신규 캠페인·IOC 없는 집계 자료이며 Mustang Panda는 이미 `groups.md`에 등재되어 있어 추가 반영 사항 없음.

60일 창이 2026-09-17~로 이동했습니다. 기존 12건 캠페인 중 최저 공개일은 "CC Switch — AI 모델 전환 공격 툴"(공개 2026-09-16)로, 창 경계와 거의 겹치지만 정책상 포함 유지(전일 판단과 동일). 신규 캠페인 없음으로 금일 총 12건 유지. 7일 창(2026-11-08~2026-11-15) 기준 🔥 해당 캠페인 없음.

## 최근 캠페인 (최근 60일)

### Storm-0940(UNC7228) — ARTEX AI 에이전트 기반 ConnectWise 공급망 침해, M365 테넌트 대량 표적화
- 귀속: 귀속 미확인 — 원문 인용: "China-state aligned actor"(Microsoft, 검증) / GTIG 인용: "overlaps with activity tracked by Microsoft as the PRC-nexus actor STORM-0940"(Google GTIG, 검증, 2026-10-30). PLA/MSS 명시 없음. GTIG는 ARTEX를 사용하는 "additional suspected PRC-nexus clusters"(미명명)도 별도로 존재한다고 서술(검증) — 특정 그룹 특정 불가로 별도 항목화하지 않음.
- 대상: (기존) 항공우주·국방, 자동차, 화학, 에너지, 금융서비스, 정부, 법률, 제조, 미디어, 군, 반도체, 소프트웨어, 기술, 싱크탱크·비영리단체 등 전 세계 수백 개 조직. ConnectWise Cloud Backup 멀티테넌트 앱 통해 2,250개 이상 M365 테넌트 대상화.
- 초기 침투: ConnectWise Cloud Backup 멀티테넌트 앱 공급망 침해 → 신뢰된 OAuth 앱 경유 다운스트림 테넌트 접근. 2026-10-10~14(피크 10-11) 8개 조직 327개 계정 대상 패스워드 스프레이. CVE 명시 없음
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

### Integrity Technology Group 연계 — 동남아 정부기관 메일함 대량 복제 및 MicroScan/FishHub 글로벌 봇넷·피싱 인프라 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 1차 출처(FBI/파트너국 공동권고, DOJ 보도자료) 미확보, 재보도만 확인. Integrity Technology Group은 과거 미 재무부(OFAC)가 Flax Typhoon 인프라 제공 혐의로 제재한 중국 기업. PLA/MSS로 승격하지 않음.
- 대상: 동남아시아 정부기관·법집행기관·의료기관·종교단체 M365/Exchange 계정
- 초기 침투: 웹 취약점 스캐닝 및 패스워드 스프레이 추정
- 주요 도구/멀웨어: MicroScan(IoT 봇넷 기반 스캐너, 미검증), FishHub(피싱 인프라, 미검증)
- 관측 시점: 공동권고 공개 2026-10-08
- 출처: 검색 결과만 확인 — FBI 등 공동권고(1차 출처 미확보), 재보도(전량 EGRESS_BLOCKED)

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

### SparroWocky 백도어 — FamousSparrow 라틴아메리카 정부 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "China-aligned"(The Hacker News) / ESET: "may be connected to China's interest..."(재보도, 원문 미검증)
- 대상: 아르헨티나·에콰도르·과테말라·온두라스·파나마·페루·푸에르토리코·베네수엘라 정부기관
- 초기 침투: 불명
- 주요 도구/멀웨어: SparroWocky(모듈형 C++ 백도어, SparrowDoor 대체)
- 관측 시점: 최소 2025-08부터, 2026-09-17 공개
- 출처: 검색 스니펫만 확인 — The Hacker News(차단), ESET(차단)

### AI 모델 전환 공격 툴 "CC Switch" — 미상 PRC-nexus 첩보 그룹
- 귀속: 귀속 미확인 — "a PRC-nexus espionage group"(Google Cloud/GTIG, 검증). 그룹 고유 명칭 미부여. PLA/MSS 언급 없음.
- 대상: 불명 — 원문에 특정 산업·국가 미기재
- 초기 침투: 해당 없음
- 주요 도구/멀웨어: CC Switch(다중 계정 순환, AI 모델 전환 자동화 툴)
- 관측 시점: 2026-09-16 공개
- 출처: [Google Cloud/GTIG](https://cloud.google.com/blog/products/identity-security/cloud-ciso-perspectives-how-google-monitors-ai-threats-advances-ai-defenses) — 2026-09-16 — fetched(이전 실행)

### VAPOR PANDA — ARTEX/DeepSeek AI 에이전트 기반 글로벌 동시다발 침투 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — "China-based targeted intrusion adversary"(CrowdStrike, 재보도 종합, 원문 미검증), 구 VexatiousTemper(2021년부터 추적)
- 대상: 정부부처, 통신사(미국·벨기에·필리핀), 제약·반도체·국방·원자력·금융 등 14개국 200개 이상 조직
- 초기 침투: 불명 — ARTEX를 DeepSeek 등으로 구동한 자동화된 정찰·침투(재보도)
- 주요 도구/멀웨어: ARTEX, BLOODALCHEMY 백도어
- 관측 시점: 캠페인 2026-10-17~10-28, 공개 2026-10-29~30
- 출처: 검색 결과만 확인 — CrowdStrike(DNS 미해석), 재보도(다수)

## 그룹 별칭 매핑
전체 누적 그룹 목록(마지막 관측일 포함)은 [`groups.md`](../groups.md) 참조. 금일 신규 그룹 추가 없음.

## 악용 CVE (패치 우선순위)
신규 없음. 전체 누적 목록은 [`exploited-cves.txt`](../exploited-cves.txt) 참조(27건, 검증 12 / 미검증 15).

## C2 도메인 (35, 누적)
신규 없음. 전체 목록은 [`blocklists/domains.txt`](../blocklists/domains.txt) 참조.

## C2 IP (31, 누적)
신규 없음. 전체 목록은 [`blocklists/ips.txt`](../blocklists/ips.txt) 참조.

## 파일 해시 (61, 누적)
신규 없음. 기존 61건은 이전 스냅샷([`snapshots/2026-08-27.md`](2026-08-27.md), [`snapshots/2026-08-28.md`](2026-08-28.md), [`snapshots/2026-09-03.md`](2026-09-03.md), [`snapshots/2026-09-07.md`](2026-09-07.md), [`snapshots/2026-09-25.md`](2026-09-25.md), [`snapshots/2026-10-01.md`](2026-10-01.md), [`snapshots/2026-10-16.md`](2026-10-16.md)) 참조.

## 호스트 IOC · LOTL 아티팩트
신규 없음(채택 기준 미달 — Citrix NetScaler 캠페인은 귀속 불명으로 미채택). 기존 항목은 [`snapshots/2026-09-07.md`](2026-09-07.md), [`snapshots/2026-10-16.md`](2026-10-16.md), [`snapshots/2026-11-03.md`](2026-11-03.md) 참조.

## 이번 실행 변경사항
- 신규 캠페인: 없음
- 신규 IOC: 없음
- 제거: 없음
- 승격(미검증→검증): 없음
- 귀속 변경: 없음
- 신규 CVE: 없음
- 신규 그룹(표 등재): 없음
- 검토 후 제외한 항목: Citrix NetScaler ADC/Gateway WHIPSHOT·SLAPSHOT 캠페인(Mandiant/GTIG, 2026-09-29, 1차 출처 본문 확보·검증 — "the threat actor"로만 기술, China/PRC/UNC/APT 귀속 전혀 없어 미채택), Vulnerability Discovery and Exploitation Trends in the AI Era(GTIG, 2026-09-30 — 특정 국가 귀속 없음), Trellix 반기 위협 보고서(2026-11-04 — 통계 자료, 신규 캠페인·IOC 없음, Mustang Panda는 이미 등재됨)
- 비고: WebFetch 3건 사용(GTIG 색인 — 성공; Citrix NetScaler 본문 — 성공, 귀속 없어 미채택; Microsoft 블로그 색인 — 성공). 6개 정기 검색 쿼리와 추가 타겟 검색 다수 수행 결과, 60일 창 내에서 PLA/MSS 또는 국가 배후로 귀속 가능한 신규 캠페인·IOC를 확인하지 못했습니다.

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
103.27.110.83
103.73.66.37
103.79.120.72
116.88.34.184
118.189.188.122
129.126.109.50
130.94.6.228
144.172.64.128
144.172.64.60
144.172.64.99
158.140.135.244
166.88.2.90
187.15.88.186
187.15.89.186
187.15.90.217
193.149.129.191
195.123.211.70
202.59.10.122
206.188.196.199
223.25.78.136
23.169.65.49
38.180.205.14
38.54.112.184
38.60.171.242
38.60.194.21
45.77.39.28
8.218.240.85
8.222.225.8
98.142.138.21
```

## 출처
- [AI-driven, large-scale nation-state campaign using ARTEX enables supply chain compromise](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — Microsoft — 2026-10-21 — fetched(이전 실행)
- [ARTEX and Friends: Enter Agentic Offensive Frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — Google GTIG/Mandiant — 2026-10-30 — fetched(이전 실행)
- [ARMORY CASTLE Exploits BeyondTrust](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — Google GTIG — 2026-10-15 — fetched(이전 실행)
- [NeedyMantis: Unpacking a post-compromise malware family used in targeted operations](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — Microsoft — 2026-09-28 — fetched(이전 실행)
- [Cloud CISO Perspectives: How Google monitors AI threats and advances AI defenses](https://cloud.google.com/blog/products/identity-security/cloud-ciso-perspectives-how-google-monitors-ai-threats-advances-ai-defenses) — Google Cloud/GTIG — 2026-09-16 — fetched(이전 실행)
- [Google Cloud Blog — Threat Intelligence 색인](https://cloud.google.com/blog/topics/threat-intelligence) — Google GTIG — 2026-11-15 조회 — fetched(색인만, 신규 국가 배후 캠페인 없음 확인)
- [Defending Against Active Exploitation of Citrix NetScaler ADC and Gateway Appliances](https://cloud.google.com/blog/topics/threat-intelligence/defending-against-active-exploitation-of-citrix-netscaler-adc-and-gateway-appliances/) — Mandiant/GTIG — 2026-09-29 — fetched(본문 확보, 귀속 없어 미채택)
- [Microsoft Security Blog 색인](https://www.microsoft.com/en-us/security/blog/) — Microsoft — 2026-11-15 조회 — fetched(색인만, 중국 귀속 신규 캠페인 없음 확인)
