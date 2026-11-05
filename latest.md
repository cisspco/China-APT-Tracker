# China State APT Campaign Snapshot — 2026-11-05 UTC

## 수집 상태
- 페치 성공: [Google Cloud Threat Intelligence 블로그 목록](https://cloud.google.com/blog/topics/threat-intelligence)(재페치 — 11건 전체 제목 확인, 전일(11-04) 이후 신규 게시물 없음, 신규 China/PRC-nexus 게시물 없음), [Microsoft Security Blog 위협 인텔리전스 목록](https://www.microsoft.com/en-us/security/blog/topic/threat-intelligence/)(재페치 — 11-03 게시물까지 확인, 그 이후 신규 게시물 없음. 11-03 "Fake-download campaign" 게시물은 금전적 동기 멀웨어로 국가 귀속 없어 검토 후 제외)
- 페치 차단: socradar.io(DNS 미응답 — 세션 네트워크 허용목록 밖으로 판단), hackread.com(DNS 미응답, 동일), vpncentral.com(DNS 미응답, 동일) — 모두 검색 스니펫에서만 확인된 2차 보도였으며 원문 미확보로 수집 제외
- 검증된 IOC: 신규 0개(누적 도메인 35·IP 31·해시 61) / 미검증 IOC: 신규 0개(누적 도메인 0·IP 0) / 신규 CVE: 0건(누적 27, 검증 12/미검증 15)

6개 정기 WebSearch 쿼리(중국 국가 배후 APT IOC, Typhoon 계열, APT31/40/41, Mustang Panda/i-Soon/Chengdu 404, CISA PRC 권고, PLA 전략지원부대)를 수행했습니다. 검색 결과는 전량 기존에 이미 반영된 캠페인의 재보도, 60일 창 밖의 과거 자료(예: 2026년 1월 Volt Typhoon 공동권고, 2026년 3~5월 SOHO 라우터 공동권고, 2026년 5월 Salt Typhoon/Twill Typhoon 확장 보도, 2026년 2월 ASD APT40 베트남어판 권고, 2026년 2월 Lotus Blossom/Notepad++ 보도, 2025년 12월~2026년 1월 Mustang Panda 외교 브리핑 위장 캠페인), 또는 검증 기준 미충족 자료(1차 출처 미확보)였습니다. GTIG/Microsoft 블로그 목록을 직접 재페치해 전일 이후 신규 게시물을 확인했으나, 수집 규칙에 부합하는 신규 중국 국가 배후 캠페인은 발견하지 못했습니다. 검색 스니펫에서 발견한 2차 보도 3건(SOCRadar Chrome/Windows 제로데이 체인, 2026-09-12 — 60일 창 내이나 1차 출처 미확보; hackread.com Mustang Panda 외교 브리핑; vpncentral.com 동남아 정부 3개 클러스터 공동공격)을 원문 확인 위해 페치 시도했으나 모두 DNS 미응답으로 차단되어 미검증 상태를 벗어나지 못했고, 수집 규칙상 미검증 자료는 1차 출처 확보 전까지 블록리스트에 반영하지 않으므로 그대로 제외했습니다.

60일 창이 2026-09-06~으로 1일 이동했으며, 기존 14건 캠페인 모두 창 내에 유지됩니다(최저 관측/공개일 캠페인인 RAVINE CASTLE·BASIN CASTLE·UNC6508 2026-09-08은 여전히 창 내). 7일 창(2026-10-29~2026-11-05) 기준 Storm-0940(UNC7228)만 🔥 유지(GTIG 2026-10-30 보고서, 6일 전).

## 최근 캠페인 (최근 60일)

### Storm-0940(UNC7228) — ARTEX AI 에이전트 기반 ConnectWise 공급망 침해, M365 테넌트 대량 표적화 🔥
- 귀속: 귀속 미확인 — 원문 인용: "China-state aligned actor"(Microsoft, 검증) / GTIG 인용: "overlaps with activity tracked by Microsoft as the PRC-nexus actor STORM-0940"(Google GTIG, 검증, 2026-10-30). PLA/MSS 명시 없음. GTIG는 ARTEX를 사용하는 "additional suspected PRC-nexus clusters"(미명명)도 별도로 존재한다고 서술(검증) — 특정 그룹 특정 불가로 별도 항목화하지 않음.
- 대상: (기존) 항공우주·국방, 자동차, 화학, 에너지, 금융서비스, 정부, 법률, 제조, 미디어, 군, 반도체, 소프트웨어, 기술, 싱크탱크·비영리단체 등 전 세계 수백 개 조직. ConnectWise Cloud Backup 멀티테넌트 앱 통해 2,250개 이상 M365 테넌트 대상화. 미국·유럽의 엔터프라이즈 소프트웨어, 산업자동화, 반도체 설계·제조, 통신사(GTIG가 Wiz 인용). 미국 정부기관, 기술, 화학·소재, 제조업(GTIG/Mandiant IR 직접 사례). ⚠️(미검증, GTIG가 CrowdStrike 공개 보도 인용) 한국 등 아시아 금융권(별도 미상 공격자로 서술, STORM-0940과 동일 귀속 미확정)
- 초기 침투: ConnectWise Cloud Backup 멀티테넌트 앱 공급망 침해 → 신뢰된 OAuth 앱 경유 다운스트림 테넌트 접근. 2026-10-10~14(피크 10-11) 8개 조직 327개 계정 대상 패스워드 스프레이. Azure Kudu/SCM 관리 API를 퍼블리싱 자격증명·스토리지/SAS/서비스 주체 자격증명으로 악용; AWS는 탈취한 IAM 사용자 자격증명 사용; Weaver OA 웹서버(Linux)는 노출된 애플리케이션 API에 유효 자격증명으로 SQL 실행. ARTEX가 탈취 자격증명을 받아 이후 단계를 자동 수행 — 계정 탈취부터 심층 시스템 접근까지 평균 약 4시간, 최단 사례 15분. CVE 명시 없음
- 주요 도구/멀웨어: ARTEX(오픈소스 멀티에이전트 LLM 펜테스트 프레임워크, Go+Next.js, 임의 AI 모델 구동 가능; 2026-10 원저자 GitHub 저장소 비공개 전환, ScopeWeaver 포크 및 상업판 "ARTEX PRO" 존재). 사후공격: 기존 OAuth/서비스 주체 앱에 자격증명 추가, 일부 ConnectWise 관리 앱의 Global Administrator 역할 자가 할당, Microsoft Graph로 ID·그룹·권한있는 역할 변경, Azure Key Vault 비밀 대량 조회, 웹셸 배포(MySQL `general_log_file` 설정 악용해 공개 경로에 `.jsp` 웹셸 작성: `cl1217.jsp`, `f1219a.jsp`, `z1219.jsp`), 프로브 파일명 `artex-probe-*`(5자리 증분 접미사), `is_admin=true` 권한 계정 생성(명명 패턴 `ArtexProbe`), curl로 webhook.site 순환 URL 491개 유출, 클라우드에서 t3.micro 인스턴스·100GB 볼륨 생성, 알림 기능 악용해 조직 내부 사용자 1,300명 이상에게 테스트 이메일 대량 발송
- 관측 시점: 최소 2026-08말부터 ARTEX 관련 활동 관측(GTIG/Wiz), 2026-10-10~14 패스워드 스프레이 피크, 2026-10-15 ConnectWise 침해 최초 보도, 2026-10-16 ConnectWise 1차 권고, 2026-10-21 Microsoft 블로그 공개, 2026-10-30 GTIG/Mandiant "ARTEX and Friends" 공개(UNC7228 명명 부여)
- 출처: [AI-driven, large-scale nation-state campaign using ARTEX enables supply chain compromise](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/) — Microsoft — 2026-10-21 — fetched(이전 실행); [ARTEX and Friends: Enter Agentic Offensive Frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — Google GTIG/Mandiant — 2026-10-30 — fetched(이전 실행, 금일 목록상 재확인)

### ARMORY CASTLE(구 UNC5221) — BeyondTrust Remote Support 제로데이 익스플로잇, SAWFLY·BARECLAW
- 귀속: 귀속 미확인 — 원문 인용: "ARMORY CASTLE, a suspected PRC-nexus espionage threat actor (formerly tracked as UNC5221)" (GTIG, 검증). PLA/MSS 명시 없음.
- 대상: 불명 — 원문에 특정 산업·국가 미기재(피해 조직 수·분야 비공개)
- 초기 침투: BeyondTrust Remote Support(구 Bomgar, 26.2.3 이하 버전) 제로데이 CVE-2026-102764(인증 없는 임의 파일 업로드) 익스플로잇
- 주요 도구/멀웨어: SAWFLY(PHP 웹셸, `mangoapi.php`), BARECLAW(SOCKS5-over-WebSocket 터널러, `ingredi_ws`), 스테이징 웹셸 `app_84304470%2Ephp`; `bt-secrets` 탈취, `zz-root-persist` 지속성 스크립트, `/usr/bin/dbus-authd` SUID 셸 사본
- 관측 시점: 제로데이 익스플로잇 2026년 8월 말, BeyondTrust 2026-10-09 SaaS 테넌트 패치, 2026-10-15 취약점 공개 및 GTIG 보고서 발행. ARMORY CASTLE(구 UNC5221)은 최소 2023-10부터 활동
- 출처: [ARMORY CASTLE Exploits BeyondTrust](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — Google GTIG — 2026-10-15 — fetched(이전 실행)

### Integrity Technology Group 연계 — 동남아 정부기관 메일함 대량 복제 및 MicroScan/FishHub 글로벌 봇넷·피싱 인프라 (FBI 등 7개국 공동권고 + DOJ 도메인 압류) ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합(1차 출처인 FBI/파트너국 공동권고 및 DOJ 보도자료 원문 미확보, 재보도만 확인): Integrity Technology Group은 과거 미 재무부(OFAC)가 "Flax Typhoon" 활동에 인프라를 제공한 혐의로 제재한 중국 기업이며, 영국도 별도 제재를 부과한 바 있음. 공동권고·압류 발표 자체가 PLA 또는 MSS를 명시했는지는 1차 출처 미확보로 확인 불가. PLA/MSS로 승격하지 않음.
- 대상: 동남아시아 정부기관·법집행기관·의료기관·종교단체의 Microsoft 365/Exchange 계정(메일함 복제); ⚠️(미검증) 미국 사우스캐롤라이나주 전력회사, 일본·폴란드 공항, 대만 가스·전력 부문 조직(MicroScan/FishHub 인프라 피해자로 거론)
- 초기 침투: 웹 취약점 스캐닝 및 Microsoft 365/Exchange 계정 비밀번호 추측(패스워드 스프레이 추정)으로 계정 접근 후, 1,300개 이상의 스크립트를 포함한 자체 제작 도구로 메일함을 대량 복제. ⚠️(미검증) MicroScan은 감염된 IoT 기기 봇넷을 이용한 인터넷 전역 취약점 스캐닝 도구로 서술됨
- 주요 도구/멀웨어: 명칭 미상의 메일함 대량 복제 툴(1,300개 이상 스크립트 포함). ⚠️(미검증) 추가 보도로 툴 명칭 특정: MicroScan(취약점 스캐너, IoT 봇넷 기반), FishHub(스피어피싱·멀웨어 배포 인프라) — FBI/DOJ가 관련 도메인 7개 압류
- 관측 시점: 공동권고 공개 2026-10-08, DOJ 도메인 압류 2026-10-08경(2026-10-09 보도 확인), 실제 활동 기간은 1차 출처 미확보로 특정 불가
- 출처: 검색 결과만 확인 — FBI 및 6개국 공동권고(1차 출처 미확보), 재보도(전량 EGRESS_BLOCKED); FBI/DOJ 도메인 압류 보도(전량 EGRESS_BLOCKED)

### UAT-11587 (Antino 백도어) — 아시아 8개국 정부·정책·시민사회 기관 대상 재부상 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합: "Talos assesses the actor as China-nexus with high confidence" (Cisco Talos 재보도 종합, 원문 EGRESS_BLOCKED로 미검증). PLA/MSS 언급 없음.
- 대상: 대만·인도·필리핀·캄보디아 등 아시아 8개국 정부·정책·시민사회 기관 — 약 350개 엔드포인트 침해 보도
- 초기 침투: 대만 학계·시민단체 대상 Gmail 위장 스피어피싱으로 최초 식별
- 주요 도구/멀웨어: Antino 백도어(Rust 컴파일) — Microsoft Graph API를 통해 Outlook/OneDrive 오브젝트를 C2 데드드롭으로 악용
- 관측 시점: 2025-09~2026-10(캠페인 지속), 최초 공개 2026-07(미검증)/2026-10-01~04경 세부사항 확대 재보도(미검증)
- 출처: 검색 결과만 확인 — Cisco Talos(blog.talosintelligence.com, 금일 프로브 대상 미포함, 전회까지 재차 프로브 결과 차단), 재보도(전량 EGRESS_BLOCKED)

### BPFdoor/Rekoobe/AVERAT — 메일보안장비 위장 통신사 침투 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합(원문 EGRESS_BLOCKED로 미검증): "likely tied to Chinese-linked espionage against telecoms". PLA/MSS 언급 없음.
- 대상: 한국·대만 통신사 — SpamSniper(한국 안티스팸 제품)·ShareTech(대만 메일보안장비) 운영사, Oracle 기반 통신 가입자/프로비저닝 플랫폼
- 초기 침투: 불명(원문 미확보) — 네트워크 경계(메일보안 게이트웨이) 장비에 기존 공개된 리눅스 백도어 BPFDoor·Rekoobe를 재사용해 배치
- 주요 도구/멀웨어: BPFDoor(변종), BPF 기반 Rekoobe 빌드, AVERAT(신규 명명, 드로퍼+임플란트 6종 빌드)
- 관측 시점: 공개 2026-10-05경(추정, 정확한 날짜 원문 미확보)
- 출처: 검색 결과만 확인 — Rapid7(차단), 재보도(전량 EGRESS_BLOCKED)

### TA419 — 미국 AI 정책 전문가 대상 자격증명 피싱 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 결과 종합(원문 EGRESS_BLOCKED로 미검증): "China-aligned". PLA/MSS 언급 없음.
- 대상: 미국 AI 정책 전문가 — 싱크탱크, 대학, 법률사무소 소속 소수 개인(10명 미만)
- 초기 침투: 유명 AI 정책가 및 Anthropic 직원 사칭 이메일로 "AI Policy Advisory Committee" 참여를 제안, 회신 유도 후 단축 URL 경유시켜 가짜 Microsoft OneDrive 로그인 페이지로 연결
- 주요 도구/멀웨어: Frameless BitB(오픈소스 브라우저-인-브라우저 피싱 툴의 수정판)
- 관측 시점: 2026-02(1차 캠페인) · 2026-07-08(2차 캠페인) ~ 현재, 공개 2026-10-02경
- 출처: 검색 결과만 확인 — Proofpoint(차단), 재보도(전량 차단)

### NeedyMantis — Storm-3069 포스트-컴프로마이즈 악성코드 프레임워크
- 귀속: 귀속 미확인 — 원문 인용: "While Microsoft assesses the activity originates from China, it has not attributed Storm-3069 to a Chinese nation-state actor." PLA/MSS 언급 없음(Microsoft, 검증)
- 대상: 통신사, 대학, 의료 비영리단체, 국제기구, 정부 계약업체
- 초기 침투: 해당 없음 — NeedyMantis는 포스트-컴프로마이즈 단계에서만 배포. Impacket 툴킷 기반 핸즈온키보드 활동 및 DLL 사이드로딩 관측
- 주요 도구/멀웨어: NeedyMantis(모듈형 포스트-컴프로마이즈 악성코드), Impacket
- 관측 시점: 최소 2025-10부터 현재까지 활동, 2026-09-28 Microsoft 공개
- 출처: [NeedyMantis: Unpacking a post-compromise malware family used in targeted operations](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — Microsoft — 2026-09-28 — fetched(이전 실행)

### Phantom Taurus — NET-STAR IIS 멀웨어 스위트 정부·통신사 첩보 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 스니펫 표현: "espionage operations align with the strategic interests of the People's Republic of China (PRC)" (Unit 42 재보도 종합). PLA/MSS 언급 없음.
- 대상: 아프리카·중동·아시아 정부기관(외교부, 대사관) 및 통신사
- 초기 침투: 불명(원문 미확보) — IIS 웹서버를 주요 거점으로 활용, CL-STA-0043 → Operation Diplomatic Specter → Phantom Taurus로 명칭 진화
- 주요 도구/멀웨어: NET-STAR(.NET 기반 신규 멀웨어 스위트, IIS 워커 프로세스 w3wp.exe 메모리 상주 컴포넌트 포함)
- 관측 시점: 활동 계보 2023-06 ~ 2024-05 ~ 현재, 공개 2026-09(정확한 날짜 원문 미확보)
- 출처: 검색 스니펫만 확인 — Unit 42(unit42.paloaltonetworks.com, 금일 포함 재차 프로브 결과 DNS 차단)

### Red Heron — WordPress·Zyxel·Ubiquiti·Gitea 연쇄 익스플로잇 정부기관 데이터 탈취 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 스니펫 표현: "Chinese-speaking threat actor linked to the Red Heron group" (Acronis TRU/GreyNoise 재보도 종합). PLA/MSS 언급 없음.
- 대상: 정부기관·법집행기관 등 49개 조직(29개국) — WordPress 경로, 996개 Zyxel GS1900 스위치(48개국) — 네트워크 장비 경로
- 초기 침투: WordPress Core wp2shell(CVE-2026-63030, CVE-2026-60137), Zyxel GS1900(CVE-2026-7273), Ubiquiti UniFi OS 체인(CVE-2026-34908/34909/34910), Gitea(CVE-2026-60004)
- 주요 도구/멀웨어: 신원 미상의 신규 Linux 루트킷, AMSI 우회, 권한 상승 도구
- 관측 시점: 최소 2026-06 초부터 활동, Zyxel 익스플로잇 2026-08-17 시작, 공개 2026-09-22경
- 출처: 검색 스니펫만 확인 — Acronis TRU(차단), GreyNoise(차단)

### UTA0565 — "Mind the (Patch) Gap, Part 2" Chrome/Windows 제로데이 체인 재사용, CLEANGULP ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 스니펫 표현: "Chinese threat group"/"China-aligned threat group" (Volexity 재보도 종합). PLA/MSS 언급 없음.
- 대상: 아시아 정부기관 등 — 홍콩 활동가 추 항퉁(Chow Hang-tung) 공개 지지를 촉구하는 위장 피싱 메일로 유인
- 초기 침투: BlueMoon 캠페인(UTA0560/JungleBamboo)과 동일한 Chrome/Windows 패치갭 제로데이 체인 — CVE-2026-85046 + CVE-2026-87491 + CVE-2026-85880
- 주요 도구/멀웨어: CLEANGULP — Microsoft Visual C Compiler로 빌드된 신규 악성코드
- 관측 시점: 2026-09-03~09-04 공격 탐지, 2026-09-21 Volexity 공개
- 출처: 검색 스니펫만 확인 — Volexity(차단)

### SparroWocky 백도어 — FamousSparrow 라틴아메리카 정부 캠페인 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 스니펫 표현: "China-aligned"(The Hacker News), ESET은 "may be connected to China's interest in monitoring how regional governments respond to growing US political, economic, and strategic engagement in Latin America"로 평가. PLA/MSS 언급 없음.
- 대상: 라틴아메리카 8개국 정부기관 — 아르헨티나, 에콰도르, 과테말라, 온두라스, 파나마, 페루, 푸에르토리코, 베네수엘라
- 초기 침투: 불명
- 주요 도구/멀웨어: SparroWocky — 모듈형 C++ 백도어, 기존 SparrowDoor 대체
- 관측 시점: 최소 2025-08부터 활동, 2026-09-17 공개
- 출처: 검색 스니펫만 확인 — The Hacker News(차단), ESET welivesecurity.com(차단)

### AI 모델 전환 공격 툴 "CC Switch" — 미상 PRC-nexus 첩보 그룹
- 귀속: 귀속 미확인 — 원문 인용: "a PRC-nexus espionage group" (Google Cloud/GTIG, Cloud CISO Perspectives, 검증). 그룹 고유 명칭 미부여. PLA/MSS 언급 없음.
- 대상: 불명 — 원문에 특정 산업·국가 미기재
- 초기 침투: 해당 없음 — 공격 후 작업 자동화 패턴(AI 모델 전환)만 기술
- 주요 도구/멀웨어: CC Switch — 다중 계정을 순환시키며 Claude·Codex·Gemini 등 AI 모델을 작업별로 전환하는 자동화 툴
- 관측 시점: 2026-09-16 공개
- 출처: [Cloud CISO Perspectives: How Google monitors AI threats and advances AI defenses](https://cloud.google.com/blog/products/identity-security/cloud-ciso-perspectives-how-google-monitors-ai-threats-advances-ai-defenses) — Google Cloud/GTIG — 2026-09-16 — fetched(이전 실행)

### BlueMoon — Chrome/Windows 패치갭 제로데이 체인 — TA412/JungleBamboo·UTA0560 ⚠️ (미검증)
- 귀속: 귀속 미확인 — 검색 스니펫 표현: "Chinese threat actors"/"China-linked"/"China-aligned"/"state-aligned". PLA/MSS 언급 없음.
- 대상: 미국 NGO, 광업 기업, 실물상품거래 기업(TA412), 반사형 XSS 취약점이 있던 미국 대학 웹사이트 방문자 등
- 초기 침투: CVE-2026-85046 + CVE-2026-87491 + CVE-2026-85880. TA412은 대학생 인턴십 문의·Association for Asian Studies 컨퍼런스 위장 스피어피싱으로 유포
- 주요 도구/멀웨어: GRIMWEDGE(UTA0560), SUPERSTOMP(JungleBamboo) → LONGTALE, GemStone(TA412, ⚠️ 미검증)
- 관측 시점: 2026-08-28 TA412 최초 사용, 2026-09-01 일반 활동, 2026-09-09 Volexity 공개
- 출처: 검색 스니펫만 확인 — Volexity(차단), Proofpoint(차단)

### AI 통합 첩보작전 고도화 — RAVINE CASTLE·BASIN CASTLE·UNC6508 (GTIG AI Threat Tracker)
- 귀속: 귀속 미확인 — 원문 인용: "RAVINE CASTLE, a PRC-nexus cyber espionage group previously known as COULEE, APT24"; "BASIN CASTLE, a PRC-nexus cyber espionage group previously tracked as BASIN and TEMP.Hex"; "UNC6508, a People's Republic of China (PRC)-nexus threat actor". PLA/MSS 언급 없음 (GTIG, 검증)
- 대상: RAVINE CASTLE — 외국 정부(외교부 등); BASIN CASTLE — 공격수명주기 전반; UNC6508 — 북미 학술·의료·군사 연구기관
- 초기 침투: RAVINE CASTLE — VMware vCenter SAML 취약점, Rubeus 기반 Kerberos 공격; BASIN CASTLE — 맞춤형 소셜엔지니어링, PowerShell 사후공격
- 주요 도구/멀웨어: Gemini 오남용 자동화 침투테스트 프레임워크(RAVINE CASTLE), 생성형 AI 통합 공격수명주기 도구(BASIN CASTLE)
- 관측 시점: 2026-09-08 공개
- 출처: [From Prompting to Autonomy: The Evolution of Adversarial AI](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai) — Google GTIG — 2026-09-08 — fetched(이전 실행)

## 그룹 별칭 매핑
전체 누적 그룹 목록(마지막 관측일 포함)은 [`groups.md`](../groups.md) 참조. 금일 신규 없음.

## 악용 CVE (패치 우선순위)
신규 없음. 전체 누적 목록은 [`exploited-cves.txt`](../exploited-cves.txt) 참조(27건, 검증 12 / 미검증 15).

## C2 도메인 (35, 누적)
신규 없음. 전체 목록은 [`blocklists/domains.txt`](../blocklists/domains.txt) 참조.

## C2 IP (31, 누적)
신규 없음. 전체 목록은 [`blocklists/ips.txt`](../blocklists/ips.txt) 참조.

## 파일 해시 (61, 누적)
신규 없음. 기존 61건은 이전 스냅샷([`snapshots/2026-08-27.md`](2026-08-27.md), [`snapshots/2026-08-28.md`](2026-08-28.md), [`snapshots/2026-09-03.md`](2026-09-03.md), [`snapshots/2026-09-07.md`](2026-09-07.md), [`snapshots/2026-09-25.md`](2026-09-25.md), [`snapshots/2026-10-01.md`](2026-10-01.md), [`snapshots/2026-10-16.md`](2026-10-16.md)) 참조.

## 호스트 IOC · LOTL 아티팩트
신규 없음. 기존 항목은 [`snapshots/2026-09-07.md`](2026-09-07.md), [`snapshots/2026-10-16.md`](2026-10-16.md), [`snapshots/2026-11-03.md`](2026-11-03.md) 참조.

## 이번 실행 변경사항
- 신규 캠페인: 없음
- 신규 IOC: 없음
- 제거: 없음
- 승격(미검증→검증): 없음
- 귀속 변경: 없음
- 신규 CVE: 없음
- 신규 그룹(표 등재): 없음
- 검토 후 제외한 항목: Fake-download campaign(Microsoft, 2026-11-03 — 금전적 동기 트로이목마 설치파일, 국가 배후 서술 없음)
- 비고: GTIG·Microsoft 블로그 목록을 직접 재페치해 전일 이후 신규 게시물을 모두 확인했으나, 수집 규칙에 부합하는 신규 중국 국가 배후 캠페인은 없었음. 검색 스니펫에서만 발견된 2차 보도 3건(socradar.io, hackread.com, vpncentral.com)의 원문 확보를 시도했으나 세 도메인 모두 DNS 미응답(세션 네트워크 허용목록 밖)으로 차단되어 미검증 상태 유지. WebFetch 예산 5건 사용(성공 2건 — GTIG/MS 블로그 목록, 차단 3건 — socradar.io/hackread.com/vpncentral.com).

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
- [ARTEX and Friends: Enter Agentic Offensive Frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks) — Google GTIG/Mandiant — 2026-10-30 — fetched(이전 실행, 금일 목록상 재확인)
- [ARMORY CASTLE Exploits BeyondTrust](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-beyondtrust) — Google GTIG — 2026-10-15 — fetched(이전 실행)
- [NeedyMantis: Unpacking a post-compromise malware family used in targeted operations](https://www.microsoft.com/en-us/security/blog/2026/09/28/needymantis-unpacking-a-post-compromise-malware-family-used-in-targeted-operations/) — Microsoft — 2026-09-28 — fetched(이전 실행)
- [From Prompting to Autonomy: The Evolution of Adversarial AI](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai) — Google GTIG — 2026-09-08 — fetched(이전 실행)
- [Cloud CISO Perspectives: How Google monitors AI threats and advances AI defenses](https://cloud.google.com/blog/products/identity-security/cloud-ciso-perspectives-how-google-monitors-ai-threats-advances-ai-defenses) — Google Cloud/GTIG — 2026-09-16 — fetched(이전 실행)
- [Google Cloud Threat Intelligence 블로그 목록](https://cloud.google.com/blog/topics/threat-intelligence) — Google Cloud/GTIG — 2026-11-05 조회 — fetched(신규 게시물 없음)
- [Microsoft Security Blog 위협 인텔리전스 목록](https://www.microsoft.com/en-us/security/blog/topic/threat-intelligence/) — Microsoft — 2026-11-05 조회 — fetched(신규 China 국가배후 게시물 없음)
- socradar.io, hackread.com, vpncentral.com — blocked(DNS 미응답, 세션 네트워크 허용목록 밖)
