## 프롬프트 유형과 선택 이유
'명확한 페르소나와 시나리오 기반의 솔루션 코드 생성 (Persona-driven, Scenario-based Solution Generation)' 형이었음. 이 유형의 특징
```
페르소나 지정: '3년 차 개발자 (10년 차 결과물 원함)'라는 명확한 역할과 기대 수준을 설정했습니다.

문제 상황 제시 (Context): '긴급 요청', '이해관계자 의견 충돌', '16시 회의'라는 구체적인 배경(Context)을 제공했습니다.

명확한 목표 (Goal): 'Figma 대신 인터랙티브한 프로토타입으로 이해관계자를 설득'이라는 뚜렷한 목표를 제시했습니다.

핵심 제약 조건 (Constraints): '영상 플레이어', '타임스탬프 댓글', '다크 모드', '데이터 테이블' 등 반드시 포함되어야 할 기능과 '수정 용이한 구조'라는 기술적 제약까지 명시했습니다.

결론: 단순 "코드 만들어줘"가 아니라, '왜(Why)' 이 코드가 필요하고 '누가(Who)' 사용할 것이며 **'어떤 문제(Problem)'**를 해결해야 하는지 알려주셨습니다. 덕분에 AI가 기획 의도를 정확히 파악하고 10년 차 시니어의 관점에서 코드를 설계할 수 있었습니다.

## 작성 위해 추가 필요 요건 (더 나은 프롬프트를 위한 제안)
이미 훌륭했지만, 다음 회의 전 더 강력한 무기를 만들고 싶다면 이런 디테일을 추가할 수 있습니다.
```
'인수 조건 (Acceptance Criteria)' 제시:

기획서가 없더라도, 각 기능의 핵심 동작 방식을 명시하는 것이 좋습니다.

(예시) "타임스탬프 댓글 기능: 1. 댓글 클릭 시 해당 영상 시간으로 이동해야 함. 2. 새 댓글은 목록 최상단에 추가되어야 함."

'Empty State (빈 상태)' 정의:

시니어 개발자는 항상 '데이터가 없을 때'를 대비합니다.

(예시) "만약 리뷰 대기 목록이 0개일 경우, 테이블 영역에 '리뷰할 영상이 없습니다'라는 메시지 표시"

기술 스택 명시 (재강조):

앞서 언급했듯, "React와 Tailwind CSS 기반으로 작성해 줘"라고 명시했다면, 바로 npx create-react-app 이후에 붙여넣을 수 있는 App.js 컴포넌트 코드를 드렸을 겁니다.
```

## 문제 해결 프롬프트 

```
[페르소나]
멀티미디어 콘텐츠 기업 '네오스트림'의 프론트엔드 개발자 3년 차임. 10년차 수준의 결과물을 원함.

[지시하게 된 맥락]
1. 지시 배경
 - 콘텐츠 운영팀으로부터 "사내 영상 리뷰 및 승인용 웹 대시보드" 제작을 긴급하게 요청 받았고 관련 기획서는 완성되지 않은 상태.
 - 기획팀은 "직관적인 UI", 디자인팀은 "트렌디한 다크 모드", 운영팀은 "데이터 밀집형 테이블"을 각각 주장해 의견 좁혀지질 않음.
 - 텍스트로만 회의를 진행하고 주장하다 보니 서로 상상하는 결과물이 달라 의사결정이 지연되었음.

2. 위협 사항
 - 디자인 툴(Figma 등)로 그리기에는 시간이 부족한데, 오늘 16시 회의 전까지 실제 작동하는 결과물이 없으면 프로젝트 착수가 무기한 연기될 위기임.

[해결 방향] 
 - 버튼 클릭 등 인터랙션이 가능한 HTML/CSS 기반의 퍼블리싱 결과물을 회의 때 보여줘서 이해관계자들을 설득하고자 함.

[지시 및 출력 양식]
 1. 지시 : "웹 프로토타입 코드(HTML, CSS, JS)" 즉시 생성할 것
 2. 출력 양식
  - 영상 플레이어 영역, 타임스탬프 댓글 기능, 승인/반려 버튼, 다크 모드 스타일 포함한 단일 페이지를 생성할 것.
  - 이 코드는 회의 시간 내에 즉석에서 수정 요청을 반영할 수 있을 만큼 구조가 명확해야함.

[추가 조건]
 1. 출력물 내용은 markdown으로도 나와야함.
```

## 프롬프트 실행 결과
<!DOCTYPE html>
<html lang="ko" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>네오스트림 | 영상 리뷰 대시보드 (프로토타입)</title>
    
    <!-- 1. Tailwind CSS 로드 (빠른 프로토타이핑 및 트렌디한 UI 구현) -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- 2. 아이콘 라이브러리 (직관성 향상) -->
    <script src="https://unpkg.com/lucide-react@latest/dist/umd/lucide.js"></script>
    
    <!-- 3. Inter 폰트 (가독성 높은 UI) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* * 10년 차의 조언: 
         * 기본 폰트를 Inter로 설정하고, Tailwind의 antialiased를 적용해 렌더링을 부드럽게 합니다.
         * 스크롤바를 UI와 어울리게 커스텀하여 다크 모드의 완성도를 높입니다.
         */
        body {
            font-family: 'Inter', sans-serif;
        }

        /* Webkit 기반 브라우저용 커스텀 스크롤바 (다크 모드) */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #1f2937; /* gray-800 */
        }
        ::-webkit-scrollbar-thumb {
            background: #4b5563; /* gray-600 */
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #6b7280; /* gray-500 */
        }
    </style>
</head>
<body class="bg-gray-900 text-gray-200 antialiased">

    <!-- 피드백 토스트 (alert() 대신 사용) -->
    <div id="feedback-toast" class="fixed top-5 right-5 bg-green-600 text-white py-3 px-6 rounded-lg shadow-xl z-50 opacity-0 transform translate-y-[-20px] transition-all duration-300 ease-out">
        <span id="feedback-message"></span>
    </div>

    <div class="flex h-screen overflow-hidden">
        
        <!-- === 사이드바 (대시보드 공통 영역) === -->
        <!-- 기획팀의 '직관성' 요구를 반영한 아이콘 기반 네비게이션 -->
        <aside class="w-20 bg-gray-950 p-4 flex flex-col items-center space-y-6">
            <!-- 로고 -->
            <div class="w-12 h-12 bg-indigo-600 rounded-full flex items-center justify-center text-white font-bold text-lg">
                NS
            </div>
            
            <!-- 메뉴 아이템 -->
            <nav class="flex flex-col space-y-4">
                <a href="#" class="p-3 bg-gray-800 rounded-lg text-indigo-400" title="대시보드">
                    <i data-lucide="layout-dashboard" class="w-6 h-6"></i>
                </a>
                <a href="#" class="p-3 text-gray-500 hover:bg-gray-800 hover:text-indigo-400 rounded-lg" title="리뷰 대기">
                    <i data-lucide="video" class="w-6 h-6"></i>
                </a>
                <a href="#" class="p-3 text-gray-500 hover:bg-gray-800 hover:text-indigo-400 rounded-lg" title="승인 완료">
                    <i data-lucide="check-circle" class="w-6 h-6"></i>
                </a>
                <a href="#" class="p-3 text-gray-500 hover:bg-gray-800 hover:text-indigo-400 rounded-lg" title="보관함">
                    <i data-lucide="archive" class="w-6 h-6"></i>
                </a>
            </nav>
            
            <!-- 하단 사용자 정보 -->
            <div class="mt-auto">
                 <img src="https://placehold.co/40x40/7c3aed/ffffff?text=U" alt="User" class="w-10 h-10 rounded-full border-2 border-gray-700">
            </div>
        </aside>

        <!-- === 메인 콘텐츠 영역 === -->
        <div class="flex-1 flex flex-col overflow-hidden">
            
            <!-- 헤더 -->
            <header class="bg-gray-900 border-b border-gray-800 p-4 flex justify-between items-center">
                <h1 class="text-xl font-semibold text-white">콘텐츠 리뷰 상세</h1>
                <div class="flex items-center space-x-4">
                    <button class="text-gray-400 hover:text-white">
                        <i data-lucide="search" class="w-5 h-5"></i>
                    </button>
                    <button class="text-gray-400 hover:text-white relative">
                        <i data-lucide="bell" class="w-5 h-5"></i>
                        <span class="absolute -top-1 -right-1 w-2 h-2 bg-red-500 rounded-full"></span>
                    </button>
                </div>
            </header>

            <!-- 스크롤 가능한 메인 영역 -->
            <main class="flex-1 overflow-x-hidden overflow-y-auto bg-gray-800 p-6 lg:p-8">

                <!-- === 1. 플레이어 및 댓글 (핵심 기능) === -->
                <!-- 
                 * 10년 차의 조언: 
                 * 메인 기능(플레이어)과 보조 기능(댓글)을 Grid로 명확히 분리합니다.
                 * lg:grid-cols-3로 데스크탑에서 3:1 비율을 유지하고, 모바일에선 1단으로 자동 스택됩니다.
                 -->
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 lg:gap-8 mb-8">
                    
                    <!-- 1-1. 영상 플레이어 및 승인/반려 버튼 (메인) -->
                    <section class="lg:col-span-2 bg-gray-900 rounded-lg shadow-lg overflow-hidden">
                        <div class="aspect-video bg-black">
                            <!-- 
                             * 실제 영상 태그입니다. controls를 활성화하여 기본 기능을 사용합니다.
                             * JS에서 이 video 태그를 제어하여 타임스탬프를 가져옵니다.
                             -->
                            <video id="main-video" class="w-full h-full" controls poster="https://placehold.co/1920x1080/000000/333333?text=Video+Player">
                                <!-- 데모용 소스. 실제로는 S3/Vimeo 등의 URL이 들어갑니다. -->
                                <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
                                Your browser does not support the video tag.
                            </video>
                        </div>
                        
                        <!-- 영상 정보 및 승인/반려 버튼 -->
                        <div class="p-6">
                            <div class="flex flex-col sm:flex-row justify-between sm:items-center gap-4">
                                <div>
                                    <span class="text-sm bg-indigo-600 text-white px-2 py-0.5 rounded-full">신규</span>
                                    <h2 class="text-2xl font-bold text-white mt-2">2025년 4분기 신작 트레일러 (1차 편집본)</h2>
                                    <p class="text-gray-400 text-sm mt-1">요청자: 마케팅팀 (김철수) / 업로드: 2025-11-13 09:30</p>
                                </div>
                                
                                <!-- 승인/반려 버튼 -->
                                <div class="flex-shrink-0 flex space-x-3">
                                    <button id="btn-reject" class="flex items-center justify-center gap-2 bg-gray-700 hover:bg-red-600 text-white font-semibold py-2 px-5 rounded-lg transition-all duration-200">
                                        <i data-lucide="x" class="w-5 h-5"></i>
                                        <span>반려</span>
                                    </button>
                                    <button id="btn-approve" class="flex items-center justify-center gap-2 bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-2 px-5 rounded-lg transition-all duration-200 shadow-lg shadow-indigo-600/30">
                                        <i data-lucide="check" class="w-5 h-5"></i>
                                        <span>승인</span>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </section>

                    <!-- 1-2. 타임스탬프 댓글 기능 (보조) -->
                    <aside class="bg-gray-900 rounded-lg shadow-lg flex flex-col max-h-[100vh] lg:max-h-[calc(100vh-10rem)]">
                        <h3 class="text-lg font-semibold text-white p-4 border-b border-gray-800">리뷰 코멘트</h3>
                        
                        <!-- 댓글 목록 (스크롤 영역) -->
                        <div id="comment-feed" class="flex-1 overflow-y-auto p-4 space-y-4">
                            <!-- JS로 동적 생성될 댓글 예시 (목업) -->
                            <div class="flex items-start space-x-3 group cursor-pointer" data-timestamp="10.5">
                                <img src="https://placehold.co/32x32/312e81/ffffff?text=A" alt="Reviewer A" class="w-8 h-8 rounded-full flex-shrink-0">
                                <div class="flex-1">
                                    <p class="text-sm text-gray-300"><strong class="text-indigo-400">@디자인팀장</strong> <span class="text-gray-500 ml-1">이(가) 댓글을 남겼습니다.</span></p>
                                    <p class="text-gray-100 mt-1">이 부분 로고 노출 시간이 너무 짧네요. 2초 정도 더 늘려주세요.</p>
                                    <span class="text-xs text-indigo-400 font-semibold group-hover:underline">@ 00:10</span>
                                </div>
                            </div>
                            <div class="flex items-start space-x-3 group cursor-pointer" data-timestamp="32.2">
                                <img src="https://placehold.co/32x32/be185d/ffffff?text=B" alt="Reviewer B" class="w-8 h-8 rounded-full flex-shrink-0">
                                <div class="flex-1">
                                    <p class="text-sm text-gray-300"><strong class="text-pink-400">@운영팀</strong> <span class="text-gray-500 ml-1">이(가) 댓글을 남겼습니다.</span></p>
                                    <p class="text-gray-100 mt-1">자막 오타 확인했습니다. "네오스트림" -> "네오스트림"</p>
                                    <span class="text-xs text-indigo-400 font-semibold group-hover:underline">@ 00:32</span>
                                </div>
                            </div>
                            <!-- /JS 동적 생성 영역 -->
                        </div>
                        
                        <!-- 댓글 입력 폼 -->
                        <form id="comment-form" class="p-4 border-t border-gray-800 bg-gray-950 rounded-b-lg">
                            <textarea id="comment-input" class="w-full bg-gray-800 border border-gray-700 rounded-lg p-3 text-sm text-gray-100 placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 resize-none" rows="3" placeholder="리뷰 코멘트를 입력하세요..."></textarea>
                            <div class="flex justify-between items-center mt-3">
                                <!-- 타임스탬프 버튼 -->
                                <button type="button" id="btn-timestamp" class="flex items-center gap-1.5 text-sm text-indigo-400 hover:text-indigo-300 font-semibold">
                                    <i data-lucide="clock" class="w-4 h-4"></i>
                                    <span id="timestamp-label">타임스탬프 추가 (00:00)</span>
                                </button>
                                <!-- 전송 버튼 -->
                                <button type="submit" class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold py-1.5 px-4 rounded-lg text-sm transition-all duration-200">전송</button>
                            </div>
                        </form>
                    </aside>
                </div>

                <!-- === 2. 데이터 밀집형 테이블 (운영팀 요구사항) === -->
                <section class="bg-gray-900 rounded-lg shadow-lg overflow-hidden">
                    <h3 class="text-lg font-semibold text-white p-4 border-b border-gray-800">전체 리뷰 대기 목록</h3>
                    
                    <!-- 
                     * 10년 차의 조언:
                     * 테이블은 overflow-x-auto로 감싸 모바일에서 가로 스크롤이 가능하게 합니다.
                     * text-sm, py-2.5, px-4 등 촘촘한(dense) 간격의 유틸리티를 사용합니다.
                     * hover:bg-gray-800으로 인터랙션을 명확히 합니다.
                     -->
                    <div class="overflow-x-auto">
                        <table class="w-full min-w-[768px]">
                            <thead class="bg-gray-950">
                                <tr>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">
                                        <input type="checkbox" class="bg-gray-800 border-gray-700 rounded text-indigo-600 focus:ring-indigo-500">
                                    </th>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">콘텐츠 명</th>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">요청자</th>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">버전</th>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">상태</th>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">마감일</th>
                                    <th class="py-2.5 px-4 text-left text-xs font-semibold text-gray-400 uppercase tracking-wider">액션</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-gray-800">
                                <!-- 목업 데이터 -->
                                <tr class="hover:bg-gray-800 transition-colors duration-150">
                                    <td class="py-2.5 px-4"><input type="checkbox" class="bg-gray-800 border-gray-700 rounded text-indigo-600 focus:ring-indigo-500"></td>
                                    <td class="py-2.5 px-4 text-sm font-medium text-white">브랜드 필름 (최종본)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">운영팀 (이영희)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">v3 (최종)</td>
                                    <td class="py-2.5 px-4">
                                        <span class="text-xs font-medium bg-yellow-600 text-yellow-100 px-2 py-0.5 rounded-full">리뷰 대기</span>
                                    </td>
                                    <td class="py-2.5 px-4 text-sm text-red-400 font-medium">2025-11-14 (D-1)</td>
                                    <td class="py-2.5 px-4 text-sm"><a href="#" class="text-indigo-400 hover:underline font-semibold">보기</a></td>
                                </tr>
                                <tr class="hover:bg-gray-800 transition-colors duration-150">
                                    <td class="py-2.5 px-4"><input type="checkbox" class="bg-gray-800 border-gray-700 rounded text-indigo-600 focus:ring-indigo-500"></td>
                                    <td class="py-2.5 px-4 text-sm font-medium text-white">SNS 숏폼 (A안)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">마케팅팀 (박지훈)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">v1</td>
                                    <td class="py-2.5 px-4">
                                        <span class="text-xs font-medium bg-yellow-600 text-yellow-100 px-2 py-0.5 rounded-full">리뷰 대기</span>
                                    </td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">2025-11-17</td>
                                    <td class="py-2.5 px-4 text-sm"><a href="#" class="text-indigo-400 hover:underline font-semibold">보기</a></td>
                                </tr>
                                <tr class="hover:bg-gray-800 transition-colors duration-150">
                                    <td class="py-2.5 px-4"><input type="checkbox" class="bg-gray-800 border-gray-700 rounded text-indigo-600 focus:ring-indigo-500"></td>
                                    <td class="py-2.5 px-4 text-sm font-medium text-white">주주총회 스케치</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">IR팀 (최수영)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">v1</td>
                                    <td class="py-2.5 px-4">
                                        <span class="text-xs font-medium bg-green-600 text-green-100 px-2 py-0.5 rounded-full">승인 완료</span>
                                    </td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">2025-11-12</td>
                                    <td class="py-2.5 px-4 text-sm"><a href="#" class="text-indigo-400 hover:underline font-semibold">보기</a></td>
                                </tr>
                                <tr class="hover:bg-gray-800 transition-colors duration-150">
                                    <td class="py-2.5 px-4"><input type="checkbox" class="bg-gray-800 border-gray-700 rounded text-indigo-600 focus:ring-indigo-500"></td>
                                    <td class="py-2.5 px-4 text-sm font-medium text-white">채용 인터뷰 (개발자편)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">인사팀 (김민준)</td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">v2</td>
                                    <td class="py-2.5 px-4">
                                        <span class="text-xs font-medium bg-red-600 text-red-100 px-2 py-0.5 rounded-full">반려</span>
                                    </td>
                                    <td class="py-2.5 px-4 text-sm text-gray-300">2025-11-10</td>
                                    <td class="py-2.5 px-4 text-sm"><a href="#" class="text-indigo-400 hover:underline font-semibold">보기</a></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </section>
            </main>
        </div>
    </div>

    <script>
        /* * [10년 차의 JavaScript 구조]
         * 1. 전역 오염을 피하기 위해 DOMContentLoaded 내부에 모든 로직을 캡슐화합니다.
         * 2. 헬퍼 함수($)를 사용하여 코드를 간결하게 유지합니다.
         * 3. 기능별로 함수(initVideo, initComments 등)를 분리하여 회의 중 수정이 용이하게 합니다.
         * 4. alert() 대신 커스텀 토스트 함수(showFeedback)를 사용하여 사용자 경험을 해치지 않습니다.
         * 5. 이벤트 위임(Event Delegation)을 사용해 동적으로 추가된 댓글에도 이벤트가 작동하게 합니다.
         */
        document.addEventListener('DOMContentLoaded', () => {

            // === 1. 유틸리티 및 헬퍼 함수 ===
            const $ = (selector) => document.querySelector(selector);
            const video = $('#main-video');
            const toast = $('#feedback-toast');
            const toastMessage = $('#feedback-message');
            let toastTimer;

            /**
             * 시간을 '00:00' 형식으로 포맷합니다.
             * @param {number} seconds - 초
             * @returns {string} MM:SS 형식의 문자열
             */
            const formatTime = (seconds) => {
                const minutes = Math.floor(seconds / 60);
                const secs = Math.floor(seconds % 60);
                return `${String(minutes).padStart(2, '0')}:${String(secs).padStart(2, '0')}`;
            };

            /**
             * 사용자에게 피드백 메시지를 보여줍니다. (alert() 대체)
             * @param {'success' | 'error' | 'info'} type - 메시지 타입
             * @param {string} message - 표시할 메시지
             */
            const showFeedback = (type, message) => {
                clearTimeout(toastTimer); // 기존 타이머 제거

                toastMessage.textContent = message;
                
                // 타입별 스타일링
                toast.classList.remove('bg-green-600', 'bg-red-600', 'bg-blue-600');
                if (type === 'success') {
                    toast.classList.add('bg-green-600');
                } else if (type === 'error') {
                    toast.classList.add('bg-red-600');
                } else {
                    toast.classList.add('bg-blue-600');
                }

                // 토스트 표시
                toast.classList.remove('opacity-0', 'translate-y-[-20px]');
                toast.classList.add('opacity-100', 'translate-y-0');

                // 3초 후 자동으로 숨김
                toastTimer = setTimeout(() => {
                    toast.classList.remove('opacity-100', 'translate-y-0');
                    toast.classList.add('opacity-0', 'translate-y-[-20px]');
                }, 3000);
            };

            // === 2. 핵심 기능 초기화 ===

            /**
             * 비디오 및 승인/반려 버튼 관련 기능을 초기화합니다.
             */
            const initVideoControls = () => {
                const timestampLabel = $('#timestamp-label');
                
                // 비디오 시간이 변경될 때마다 타임스탬프 버튼 텍스트 업데이트
                if (video) {
                    video.addEventListener('timeupdate', () => {
                        const currentTime = formatTime(video.currentTime);
                        timestampLabel.textContent = `타임스탬프 추가 (${currentTime})`;
                    });
                }

                // 승인/반려 버튼
                $('#btn-approve')?.addEventListener('click', () => {
                    showFeedback('success', '영상이 [승인] 처리되었습니다. (API 호출 시뮬레이션)');
                    // TODO: 실제 API 호출 로직 (e.g., fetch('/api/approve', ...))
                });
                
                $('#btn-reject')?.addEventListener('click', () => {
                    showFeedback('error', '영상이 [반려] 처리되었습니다. (API 호출 시뮬레이션)');
                    // TODO: 실제 API 호출 로직
                });
            };

            /**
             * 댓글 시스템(입력, 출력, 타임스탬프 이동)을 초기화합니다.
             */
            const initCommentSystem = () => {
                const commentForm = $('#comment-form');
                const commentInput = $('#comment-input');
                const commentFeed = $('#comment-feed');
                const timestampBtn = $('#btn-timestamp');
                let timestampToAdd = 0; // 타임스탬프 버튼 클릭 시 저장될 시간

                // [기능] 타임스탬프 버튼 클릭
                timestampBtn?.addEventListener('click', () => {
                    timestampToAdd = video.currentTime;
                    const timeStr = formatTime(timestampToAdd);
                    
                    // 입력창에 타임스탬프 추가 및 포커스
                    commentInput.value = `@${timeStr} ${commentInput.value}`;
                    commentInput.focus();
                    showFeedback('info', `타임스탬프(${timeStr})가 추가되었습니다.`);
                });

                // [기능] 댓글 폼 전송
                commentForm?.addEventListener('submit', (e) => {
                    e.preventDefault(); // 폼 기본 동작(새로고침) 방지
                    const commentText = commentInput.value.trim();

                    if (!commentText) {
                        showFeedback('error', '코멘트 내용을 입력해주세요.');
                        return;
                    }

                    // 새 댓글 DOM 생성
                    const newComment = createCommentElement(commentText, timestampToAdd);
                    commentFeed.prepend(newComment); // 최신 댓글을 맨 위에 추가

                    // 폼 초기화
                    commentInput.value = '';
                    timestampToAdd = 0; // 타임스탬프 초기화
                    commentFeed.scrollTop = 0; // 스크롤을 맨 위로
                    showFeedback('success', '코멘트가 등록되었습니다.');
                });

                // [기능] 댓글 클릭 시 비디오 이동 (이벤트 위임)
                commentFeed?.addEventListener('click', (e) => {
                    // 클릭된 요소에서 가장 가까운 [data-timestamp] 속성을 가진 부모를 찾음
                    const commentWrapper = e.target.closest('[data-timestamp]');
                    
                    if (commentWrapper && video) {
                        const timestamp = parseFloat(commentWrapper.dataset.timestamp);
                        if (!isNaN(timestamp)) {
                            video.currentTime = timestamp;
                            video.play();
                            showFeedback('info', `영상 시간을 ${formatTime(timestamp)}로 이동합니다.`);
                        }
                    }
                });

                /**
                 * 새 댓글 DOM 요소를 생성합니다.
                 * @param {string} text - 댓글 텍스트
                 * @param {number} timestamp - 타임스탬프 (초)
                 * @returns {HTMLElement} 생성된 div 요소
                 */
                const createCommentElement = (text, timestamp) => {
                    const timeStr = formatTime(timestamp);
                    
                    // 템플릿 리터럴을 사용해 HTML 구조를 만듭니다.
                    // 회의 중 수정 요청 시 이 부분의 구조만 변경하면 됩니다.
                    const div = document.createElement('div');
                    div.className = 'flex items-start space-x-3 group cursor-pointer animate-fade-in'; // (애니메이션은 CSS로 추가 필요)
                    div.dataset.timestamp = timestamp;

                    div.innerHTML = `
                        <img src="https://placehold.co/32x32/7c3aed/ffffff?text=U" alt="Current User" class="w-8 h-8 rounded-full flex-shrink-0">
                        <div class="flex-1">
                            <p class="text-sm text-gray-300"><strong class="text-indigo-400">@나 (방금)</strong></p>
                            <p class="text-gray-100 mt-1 whitespace-pre-wrap">${text}</p>
                            ${timestamp > 0 ? `<span class="text-xs text-indigo-400 font-semibold group-hover:underline">@ ${timeStr}</span>` : ''}
                        </div>
                    `;
                    return div;
                };
            };

            // === 3. Lucide 아이콘 로드 ===
            // data-lucide 속성을 가진 모든 태그를 찾아 아이콘으로 변환합니다.
            if (typeof lucide !== 'undefined') {
                lucide.createIcons();
            }

            // === 4. 기능 실행 ===
            initVideoControls();
            initCommentSystem();
            
            console.log('네오스트림 리뷰 대시보드 프로토타입 초기화 완료.');
        });
    </script>
</body>
</html>
