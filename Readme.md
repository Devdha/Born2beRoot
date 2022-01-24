# Born2beroot

BH(Mandatory): 12.06  
Circle: 01  
Date: 2022/01/13 → 2022/01/23  
Description: This project aims to introduce you to the wonderful world of virtualization.  
Skills: Network & system administration, Rigor  
XP: 577  
hours: 40  

## Subject

[https://cdn.intra.42.fr/pdf/pdf/31621/en.subject.pdf](https://cdn.intra.42.fr/pdf/pdf/31621/en.subject.pdf)

[https://github.com/chichoon/subject_ko/blob/born2beroot/born2beroot/born2beroot_ko.md](https://github.com/chichoon/subject_ko/blob/born2beroot/born2beroot/born2beroot_ko.md#Chapter-6)

## Evaluation

[https://tonyhan18.tistory.com/218](https://tonyhan18.tistory.com/218)

## 요구사항

### 제출

- 과제 제출 시, `git` 저장소의 루트에 `signature.txt`(가상머신의 디스크 서명) 제출 ✔️

### 가상 머신

- `Virtualbox` (사용이 불가능 한 경우, `UTM`) 사용은 필수 ✔️
- 그래픽 인터페이스 사용 금지 ✔️
- `Debian` 또는 `CentOS`, 최신 stable 버전 하나 선택 ✔️
- `Debian`은 `AppArmor`, `CentOS`는 `SELinux`를 시작 시에 구동 ✔️
- `LVM`을 이용하여 최소 2개의 암호화된 파티션 생성 ✔️
- `aptitude`와 `apt`의 차이점 인지 ✔️
- `SELinux` 또는 `AppArmor`이 무엇인지 알고 있어야 함 ✔️
- `SSH` 서비스는 4242포트에서만 작동, `SSH`를 이용한  `root` 연결 비허용 ✔️
- `SSH` 동작 테스트, 동작 원리 인지 ✔️
- 4242 포트만 열려있어야 함(`UFW` 방화벽을 이용하기 때문에) ✔️
- 가상 머신 실행 시, 방화벽 활성화(`CentOS`는 기본 방화벽 대신 `UFW` 사용(`DNF`를 이용하여 설치)) ✔️

### 호스트, 유저

- 호스트명은 로그인 아이디 뒤에 42를 붙인 형식, 동료 평가 중 호스트명 변경할ex 수 있어야 함 ✔️
- 강력한 비밀번호 체계 구현
    - 비밀번호는 30일마다 소멸되어야 한다. ✔️
    - 비밀변호 변경을 위한 최소 기간은 이틀로 설정되어야 한다. ✔️
    - 유저는 비밀번호 소멸 7일전 경고 메세지를 받아야 한다. ✔️
    - 비밀번호는 10글자 이상, 대문자와 숫자를 포함해야 한다. ✔️
    그리고, 같은 글자가 3개 이상 연속될 수 없다. ✔️
    - 비밀번호에 유저명이 포함되면 안 된다. ✔️
    - 이 규칙은 루트 계정에는 적용되지 않는다. : 비밀번호는 이전 비밀번호에 포함되지 않는 문자를 최소 7개 이상 포함하여야 한다. ✔️
    - 루트 계정 비밀번호 또한 이 규칙을 따라야 한다. ✔️
- 설정 파일들을 모두 세팅한 후, 루트 계정을 포함한 모든 계정의 비밀번호를 바꿔주어야 한다. ✔️
- 엄격한 규칙을 따라, `sudo` 를 설치하고 설정
    - `sudo` 인증 시, 비밀번호가 틀릴 때 3번까지만 시도할 수 있다. ✔️
    - `sudo` 권한 사용 중, 비밀번호가 틀리면 설정한 오류 메세지가 출력되어야 한다. ✔️
    - `sudo` 권한을 이용하여 수행한 명령어는 입출력 모두 기록되어야 한다. ✔️
    해당 기록은 `var/log/sudo/` 위치에 `log` 파일로 저장되어야 한다. ✔️
    - 보안 상의 문제로 인해, TTY 모드는 활성화 되어야 한다. ✔️
    - 마찬가지로 보안 상의 문제로 인해, `sudo` 권한으로 이용할 수 있는 폴더 경로는 제한되어야 한다.  ✔️
- 루트 사용자 외에도, 내 로그인 아이디를 유저명으로 사용하는 유저가 있어야 한다. ✔️
이 유저는 반드시 `user42`와 `sudo` 그룹에 포함되어야 한다. ✔️

### 출력

- `monitoring.sh`라는 간단한 스크립트를 작성하고, `bash` 환경에서 작동하여야 한다.
- 서버가 시작될 때, 스크립트는 모든 터미널에 아래 목록의 내용을 10분에 한 번씩 보여야 한다.
(`wall`을 참고)
배너는 선택사항이고, 오류가 보이면 안된다.
    - 사용하는 운영체제의 아키텍쳐와 커널 버전 ✔️
    - 물리 프로세서의 개수 ✔️
    - 가상 프로세서의 개수 ✔️
    - 서버 내에서 사용가능한 램과 가동률을 백분율로 표시 ✔️
    - 서버 내에서 사용가능한 메모리와 가동률을 백분율로 표시 ✔️
    - 프로세서들의 가동률을 백분율로 표시 ✔️
    - 마지막 부팅 시간과 날짜 ✔️
    - `LVM`의 활성화 여부 ✔️
    - 활성화된 연결의 수 ✔️
    - 서버를 사용하고 있는 유저의 수 ✔️
    - 서버의 IPv4 주소와 MAC 주소 ✔️
    - sudo로 실행된 커맨드의 수 ✔️
    
    동료 평가 시, 위 스크립트의 동작 방식을 설명하도록 질문 받을 것이며, 수정하지 않고 중단시킬 수 있어야 한다.(`cron`을 검색해봐라)
    
    ![b2br_2.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/b2br_2.png)
    
- `head -n 2 /etc/os-release`, `ss -tun1p` 명령어로 이번 과제의 요구사항을 체크할 수 있다.

### 보너스

- 파티션을 아래 이미지와 같은 구조로 만들어 보자.
    
    ![Screen Shot 2022-01-13 at 8.00.06 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-13_at_8.00.06_PM.png)
    
- 우측 서비스를 이용하여 동작하는 `WordPress` 웹 사이트를 설정해라: lighttpd, MariaDB, and PHP. ✔️
- 유용하다고 판단하는 서비스를 사용해봐라(`NGINX` / `Apache2` 제외), 평가 시 합당한 이유를 제시해야 한다. ✔️
(추가적인 서비스 구성 시, `UFW`룰 아래에서 필요한 포트를 더 열 수 있다.)
- 보너스 파트는 필수 파트가 오류 및 오작동 없이 잘 작동할 때만 고려된다. ✔️

## 구현

- VirtualBox를 이용한 가상환경 설정
    
    ![Screen Shot 2022-01-24 at 4.20.38 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-24_at_4.20.38_PM.png)
    
- Partition
    
    보너스 파트에서 요구하는 바와 같이 파티션 설정
    
    ![Screen Shot 2022-01-24 at 4.16.40 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-24_at_4.16.40_PM.png)
    
- SSH Connection
    
    SSH로 4242 포트에 접근하여 가상 환경 원격 접속
    
    ![Screen Shot 2022-01-24 at 4.17.02 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-24_at_4.17.02_PM.png)
    
- System monitoring
    
    [monitoring.sh](http://monitoring.sh) 파일을 생성하여 시스템 모니터링(`cron` 명령어를 이용하여 10분마다 확인)
    
    ![Screen Shot 2022-01-24 at 4.17.34 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-24_at_4.17.34_PM.png)
    
- Wordpress Web
    
    보너스 파트에서 요구하는 Wordpress Web을 구현하기 위해 `Lighttpd`, `MariaDB`, `PHP`, `Wordpress`를 설치하여 가상환경에서 구동
    
    - 웹 서버: `Lighttpd`
    - 데이터베이스: `MariaDB`
    
    ![Screen Shot 2022-01-24 at 4.18.16 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-24_at_4.18.16_PM.png)
    
- Git server
    
    유용한 서비스로 `Git` 을 선택, 현업에서 사용 가능한 서비스로 고려되었다.
    
    서버 내에 `/srv/git/` 디렉토리를 생성하여 깃 레포를 관리하였음
    
    기본적인 설정만 하였으며, 접속 방식은 여러가지가 있지만 위에서 설정한 SSH 방식으로 접속
    
    아래 사진은 `clone` 및 `push` 예시
    
    ![Screen Shot 2022-01-24 at 4.20.15 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-24_at_4.20.15_PM.png)
    

*(치팅 방지를 위해 구현 방식은 개인 노션에 정리하였습니다.)*
        

## 새로운 개념

- Virtual box
    
    오라클이 배포하는 컴퓨터 가상화 프로그램
    
- 가상머신
    - 가상 머신이란?
        
        물리적으로 존재하는 컴퓨터가 아닌, 다른 컴퓨터가 만들어내는 가상의 컴퓨터
        (즉, 컴퓨터 안에 컴퓨터)
        
        가상 머신은, 프로세스 가상 머신과 시스템 가상 머신으로 나뉘는데 과제에서 사용하는 개념은 시스템 가상 머신이다.
        
        가상화는 물리적으로 한 대의 베어메탈(어떠한 소프트웨어도 설치되지 않은 하드웨어) 위에서 다수의 가상 베어메탈을 만들 수 있는 일련의 기술을 의미한다.
        
        즉, 가상의 하드웨어를 만들어주는 기술인데, 그 가상의 하드웨어 위에 운영체제를 설치하여 사용할 수 있다.
        
        이는 결과적으로 하나의 하드웨어에서 여러 개의 운영체제 실행을 가능하게 한다.
        
    - 가상 머신 사용 목적
        - 하나의 컴퓨터로 동시에 서로 다른 2개 이상의 운영체제를 실행하고 싶을 때
        - 하나의 컴퓨터 자원을 여러 명에게 나눠줘야 하고 상호간 간섭을 없애고 싶을 때
        - 컴퓨터의 다른 부분에는 영향을 주지 않는 독립 환경을 만들고 싶을 때
    - 단점
        - 가상 머신이 물리 컴퓨터 하드웨어에 간접적으로 접근하여 효율성이 낮음
    - 구현 방식
        - 에뮬레이션
        모든 부품의 모든 기능을 소프트웨어적으로 구현하는 방식
            
            가상 속도가 떨어지는 방식이나, 범용성은 뛰어나다.
            
        - 가상화
        CPU 등 주요 부품의 구현에서 하드웨어의 기능 지원을 받는 방식
            
            속도가 빠르다는 장점이 있으나, 하드웨어 기능에 종속되기 때문에 범용성이 상대적으로 떨어진다.
            (실제 컴퓨터가 처리할 수 있는 기계어 세트에서 벗어나면 가상 CPU를 지원할 수 없다.)
            
        - 반가상화
        에뮬레이션/가상화를 포기하고, 가상 머신 내에 설치될 OS를 수정하거나 전용 드라이버를 사용해 하드웨어에 직접 접근하는 방안을 별도로 마련하는 방식
            
            속도가 가장 빠르나, 하드웨어 기능 뿐 아니라 운영체제 및 드라이버에도 종속성이 되기에 범용성은 가장 떨어진다.
            
    - 하이퍼바이저(Hypervisor)
        
        우리가 알고 있는 운영 체제는 하드웨어를 제어하는데, 다수의 운영 체제가 하나의 물리 환경에서 어떻게 동작하는 걸까?
        
        이를 가능하게 하는 것이 바로 하이퍼바이저라는 소프트웨어 또는 플랫폼이다.
        
        하이퍼바이저는 컴퓨터의 운영 체제 및 응용프로그램을 물리적 하드웨어에서 분리하는 기술이다.
        하이퍼바이저는 하드웨어로 부터 제공되는 물리적인 레이어를 추상화해주고, 사용자는 그 위에서 가상머신을 통해 가상화된 물리자원들을 기존과 동일한 방식으로 사용할 수 있다.
        
        ![Screen Shot 2022-01-21 at 7.51.58 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-21_at_7.51.58_PM.png)
        
        > 위 그림에서 하이퍼바이저는 `Virtualization Layer`에 위치하며, 하위 하드웨어 계층과 가상머신 계층 사이에서 인터페이스 역할을 해주게 된다.
        > 
        
        하이퍼바이저는 하드웨어 전체를 관장할 뿐 아니라, 가상머신들 또한 관리하는 중간관리자라고 할 수 있다. 그래서 하이퍼바이저를 가상 머신 모니터라고 부르기도 한다.
        
        - Type 2
            
            위 사진은 Type 1 하이퍼바이저에 속하지만 Virtualbox는 Type 2 하이퍼바이저에 속하며, 운영체제 위에 하이퍼바이저가 있고, 그 위에 게스트 운영체제가 돌아가는 형태이다.
            
            ![Screen Shot 2022-01-21 at 8.06.20 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-21_at_8.06.20_PM.png)
            
        
- Disk signature
    
    디스크 서명은 하드 디스크 또는 기타 저장 장치의 MBR에 저장된 고유한 식별 번호
    (과제 제출자가 생성한 디스크 서명과 보여주는 과제의 디스크 서명이 동일한 지 대조하는 이유)
    
- Linux
    - Unix 계열의 운영체제
    - 공개 운영체제
    - PC용 OS보다 안정적이고, 보안에서도 우수한 성능을 보인다.
    - 다양한 네트워킹 기술 제공, 서버용으로 적합
    - 배포판이 아닌 리눅스 자체는 무료
- Debian(OS)
    - Debian: 데비안 프로젝트에서 개발하고 있는 리눅스 배포판
        - 적극적인 `비자유(클로즈드, 사유) 소스 소프트웨어` 배제
        - 긴 업데이트 주기
            
            기업이나 재단 등 주체가 있지 않고 자발적인 커뮤니티에서 만드는 배포판으로 프로그램의 업데이트가 늦다.
            
            안정성을 우선시하여, 포함되는 소프트웨어들을 보수적으로 채용함
            
            `Stable` 배포판에서 사용하는 저장소는 `experimental`, `unstable`, `testing` 저장소를 거쳐 보안 및 버그 검사를 비롯하여 안정성 시험을 마친 후 채택
            
        - 기업에서 요구하는 수준의 사후지원을 받기 힘들다.
        - 개인 무료 사용자 서버용으로 인기가 매우 높으며, 사용법이 다양한 곳에 기술되어 있어 진입장벽이 낮고, 초보 리눅스 유저들이 접근하기 쉽다.
        - 쉬운 유지보수
            
            프로그램들을 `deb`라는 패키지에 묶어서 관리하기 때문에 유지보수가 쉽다.
            (`DEB` 포맷과 `adkg/APT` 패키지 매니저 사용)
            
            - deb 패키지
                
                deb 패키지 저장소는 stable, testing, unstable, experimental로 나뉜다.
                
                - stable
                    - testing에 있던 버전이 stable로 내려올 때까지 기존 배포판에서 보안 패치 위주로만 제공
                - testing
                    - 차기 배포판을 만들기 위한 준비 공간
                    - 어느 정도 안정성이 검증되면 프로그램들이 자주 업데이트 됨
                - unstable
                    - 항상 코드네임이 **'sid'**
                    - 프로그램이 잘 작동되는지 확인하는 역할이므로 deb 패키지 업데이트가 꼬박꼬박 이루어짐
                    - experimental에서 한 단계 걸쳐 저장소로 들어가기 때문에 다른 리눅스 배포판에서 제공되는 업데이트 정도의 안정성은 있음
                - experimental
                    - 작동하는 것을 보장하지 못함(실험소)
            - debian package 배포
                - stable 배포판에 포함된 패키지
                    
                    데비안 배포판의 최신 공식 릴리즈, 안정적이고 잘 테스트된 소프트웨어
                    
                - testing 배포판에 포함된 패키지
                    
                    다음 stable 배포판의 일부가 될 예정인 패키지를 포함한다.
                    unstable의 패키지가 testing에 추가되기 전 엄격한 기준을 따라야 하며, “testing” 배포판은 보안 업데이트를 받을 수 없다.
                    
                - unstable 배포판에 포함된 패키지
                    
                    데비안의 가장 최근 패키지를 포함하며, 패키지가 안정성과 품질에 대한 기준을 충족하면 testing에 포함된다.
                    
                    “testing” 배포판과 마찬가지로 보안 지원을 받을 수 없다.
                    
        - 파일 시스템: `EXT4`(16TB 까지 지원)
        - 업그레이드가 수월하다.
- CentOS
    - Community Enterprise Operating System(CentOS)
        - RHEL(레드햇 엔터프라이즈 리눅스)에서 파생된 리눅스의 배포판
        - RHEL의 소스를 그대로 사용하기 때문에, OS 버전, Kernel 버전, 패키지 구성이 같다.
        - 서버용 운영체제로 인기가 매우 높으며 서버용으로 리눅스를 운영할 목적이라면 대부분 CentOS를 사용하게 된다.
        - 페도라 리눅스가 선구적인 기술을 너무 많이 도입하다 RHEL을 제대로 반영하지 못하게 되어, RHEL을 완벽에 가깝게 반영하는 것을 목적으로 만든 배포판
        - CentOS는 RHEL과 달리 커뮤니티 차원에서 제공되기 때문에 사후 지원이 없다.
        (그렇기에, 안정성, 유지, 비용면에서 RHEL 서비스를 이용하는 것이 저렴하다.)
        - RHEL 마이너 업데이트 시, 해당 버전에 포함된 보안 버그 수정 사항등은 CentOS 신규 버전 릴리즈 전까지 업데이트 되지 않아 공백이 발생한다.
        - RHEL을 유료로 판매하자, 몇몇 사람들이 소스코드를 가지고 레드햇 관련 상표권을 모두 제거하고 만든 것이 CentOS이다.(그래서 무료지만, 기술 지원이 없다.)
        - 패키지 관리에 `RPM` 포맷과 `YUM/DNF` 패키지 매니저 사용
        - 파일 시스템: `XFS`(확장 가능한 고 가용성 파일 시스템)
- AppArmor & SELinux
    
    둘 모두 Security framework이며, LSM(Linux Security Module)을 기반으로 구현됨
    
    - AppArmor: Application Armor의 약자
        - 시스템 관리자가 프로그램 프로필 별로 프로그램의 역량을 제한할 수 있게 해주는 리눅스 커널 보안 모듈
        - SUSE 계열, 데비안 계열에서 사용
        - MAC 적용(전통 Linux는 DAC)
        - 개별 응용 프로그램을 보호하는 일에 집중
        - 응용 프로그램 단위의 보안 모델 구현
        - AppArmor은 SELinux를 대체하는 한 부분으로서 제공됨
        - Debian에 기본적으로 설치되어 있으나, 없다면 `apt install apparmor apparmor -utils` 를 통해 설치 가능
        - `aa-enabled` 명령어를 통해 활성화 여부 확인 가능
        - `enforce` 모드와 `complain` 모두 존재
            - `enforce` : 허가되지 않은 파일에 접근하는 것을 거부
            - `complain` : 실질적인 보안을 제공하지 않음 / 어플리케이션이 해야 할 행동이 아닌 다른 행동을 하는 경우 로그를 남긴다.
            - `sudo aa-status` 를 통해 현재 상태 확인 가능
        
        ```cpp
        sudo dpkg -l apparmor // 설치 확인 명령어
        
        sudo apt istall apparmor // 설치 명령어
        
        sudo apt install apparmor-utils // 유틸 설치 명령어
        
        aa-enabled // 활성화 여부 확인
        
        sudo aa-genprof binary_file_path // 프로필 생성
        
        aa-status // apparmor 상태 확인
        ```
        
    - SELinux
        - Security-Enhanced Linux의 약자
        - 미 국방부 스타일의 강제 접근 제어(MAC)를 포함한 접근 제어 보안 정책의 매커니즘을 제공하는 리눅스 커널 보안 모듈
        - 레드햇 계열(RHEL, Fedora, CentOS)에서 사용
        - MAC 적용(전통 Linux는 DAC)
        - 시스템 전체에 보안 설정
    - 차이점
        - 파일에 레이블을 적용하는 SELinux와 달리, AppArmor은 파일 경로를 통해 작동
        - SELinux는 경로 대신 아이노드 번호로 파일 시스템 객체들을 구별
        (하드 링크 생성 시, 아이노드에 참조되는 데이터가 같기 때문에 SELinux는 기존 파일과 동일하게 인식하는 것과 달리 AppArmor에서는 접근 가능)
    - 접근 통제( `MAC` 와  `DAC`)
        - 접근 통제
            - 운영체제에서 접근 통제는 디렉토리, 파일, 네트워크 소켓 같은 시스템 자원을 적절한 권한을 가진 사용자나 그룹이 접근하고 사용할 수 있게 통제하는 것을 의미한다.
            - 접근 통제에서 시스템 자원을 객체라고 하며, 자원에 접근하는 사용자나 프로세스를 주체라고 정의한다.
        - DAC (임의 접근 제어, Discretionary Access Control)
            - 시스템 객체에 대한 접근을 사용자 또는 그룹의 신분을 기준으로 제한
            - 객체의 소유자가 다른 주체에 대한 접근 권한을 설정할 수 있다.
            (소유자의 판단에 의해 권한을 줄 수 있다.)
            - 소유자가 임의로 접근 권한을 지정하므로, 사용자의 권환을 탈취 당하면 사용자가 소유한 모든 객체의 접근 권한을 가질 수 있다는 치명적인 문제가 있다.
            (특히, root 계정 탈취 시 시스템을 완벽하게 장악할 수 있다.)
        - MAC(강제 접근 제어, Mandatory Access Control)
            - 미리 정해진 정책과 보안 등급에 따라 주체에게 허용된 접근 권한과 객체에게 부여된 등급을 비교하여 접근을 통제하는 모델
            - 높은 보안을 요구하는 정보는 낮은 보안 수준의 주체가 접근할 수 없으며, 소유자라고 해도 정책에 어긋나면 객체에 접근할 수 없으므로 강력한 보안을 제공
- LVM
    - Logical Volume Manager의 약자
    논리 볼륨을 효율적이고 유연하게 관리하기 위한 커널의 한 부분이자 프로그램
    - 기존 방식은 파일 시스템을 블록 장치에 직접 접근해서 읽고 쓰기를 헀다면,
    LVM은 파일시스템이 LVM이 만든 가상의 블록 장치에 읽고 쓰기를 한다.
        
        이와 같은 방식을 사용하는 이유는 LVM이 물리적 저장공간 이상의 추상적 레이어를 생성하여 논리적 저장공간을 생성할 수 있게 해줍니다.
        
        직접 물리 스토리지를 사용하는 것보다 다양한 측면에서 유연성을 제공하는데,
        유연한 용량 조절, 크기 조정이 가능한 스토리지 풀, 편의에 따른 장치 이름 지정, 디스크 스트라이핑, 미러 볼륨 등을 제공한다.
        
        기존 방식을 통해 용량을 추가하고 싶을 경우, 아래와 같이 복잡한 작업이 필요했지만,
        `추가 디스크를 장착하여 볼륨 생성 → 파티션 생성 및 포맷 → 파티션 마운트 → 데이터 이동 → 기존 파티션 언마운트 → 새 파티션 마운트`
        
        LVM을 사용할 경우, 아래와 같이 처리할 수 있다.
        `추가 디스크 장착 → 파티션 생성 및 물리 볼륨 생성 → 물리 볼륨을 볼륨 그룹에 추가 → 기존 논리 볼륨 사이즈를 증가`
        
    - 리눅스 안에서는 하나의 디스크를 여러 파티션으로 분할하여 파일 시스템을 이용해 특정 디렉토리와 연결시켜 사용한다.
        
        파티션을 논리적인 개념인 볼륨으로 나눠서 더 유동적으로 디스크 용량을 관리할 수 있다. 
        볼륨은 기본적으로 단일 파티션에 존재하게 되지만, 다수의 파티션을 하나의 볼륨으로 관리할 수도 있다. 
        그래서 여러 개의 파티션을 합치저나 분할하기에 용이하다.
        
    - 파티션
        
        디스크는 파티션이라는 논리적인 크기로 분할 / 통합하여 사용한다.
        하나의 디스크를 여러 개로 분할하기도, 여러 개의 디스크를 하나로 통합하기도 한다.
        
        파티션은 고정적이고 물리적인 개념이 강하며, 한 번 크기를 설정하면 변경하거나 추가하기 힘들고,
        OS는 각 파티션을 별도의 디스크처럼 인식한다.
        
    - 볼륨
        
        파일 시스템으로 포맷된 디스크 상의 저장 영역이라고 하며 파티션과 유사한 개념이지만 다르다.
        
        볼륨은 디스크의 단일 파티션에 존재하며 파티션보다 논리적으로 유동적이다.
        우리는 하나의 디스크를 여러 개의 파티션으로 나누어 사용할 수 있다.
        이때, 볼륨은 파티션마다 하나씩 존재하기도, 여러 파티션에 하나만 존재할 수도 있다.
        
- aptitude와 apt의 차이
    - APT(Advanced Packaging Tool)
        - 소프트웨어 설치와 삭제를 지원하는 무료 오픈소스 소프트웨어
        - Debian의 .deb 패키지를 지원하기 위해 디자인 되었지만, RPM Package Manage와 호환된다.
        - GUI 없이 CLI로만 사용이 가능하다.
    - Aptitude
        - 발전된 패키징 툴이며, UI를 지원한다.
        - APT와 같이 Debian을 위해 만들어졌지만, RPM 기반 배포판에서도 사용할 수 있다.
    - 공통점
        - 둘 모두 유명한 패키지 관리 툴이다.
        - 패키지와 관련된(설치, 제거, 검색 등) 작업에 최적화 되어있다.
        - 대부분의 apt-get의 명령과 같이 작동할 수 있다.
    - 차이점
        
        
        | Aptitude | Apt |
        | --- | --- |
        | high-level package manager | lower-level package manager |
        | Apt와 달리 기능이 통합되어 있다. | 각 기능이 apt-get, apt-mark 등의 커맨드로 나뉜다. |
        | 커맨드 라인을 포함한 반응형 UI를 제공한다. | 커맨드 라인만 제공한다. |
        | 충돌이 일어나도 조정가능한 부분을 추천해주고 충돌을 제거한다. | 충돌이 일어나면 명령을 끝내버린다. |
        | 패키징 과정을 자동화하여 쉽게 작업하도록 도와준다. | 제대로된 사용을 위해 많은 지식을 요구한다. |
    
- SSH
    - SSH(Secure Shell)
        
        원격 호스트에 접속하기 위해 사용되는 보안 프로토콜
        
        기존 원격 접속은 “텔넷”이라는 방식을 사용했는데, 암호화를 제공하지 않아 보안상 취약점을 가지고 있었다. 때문에 이를 암호화하는 SSH 기술이 등장했고 현재 원격 접속 보안을 위한 필수요소로 자리잡고 있다.
        
        클라우드 서비스에서 제공되는 서버는 기본적으로 원격 접속으로 접근하고 사용하기 때문에 서버 생성시 필수적으로 SSH 보안 과정을 거친다.
        
    - SSH의 작동 원리
        
        SSH를 구성하는 핵심 키워드는 `Key` 이다.
        
        클라이언트(유저)와 호스트(서버)는 각각의 키를 보유하고 있으며, 이 키를 이용해 연결 상대를 인증하고 안전하게 데이터를 주고 받게 된다.
        
        키를 생성하는 방식은 두 가지가 있는데, `대칭키`와 `비대칭키` 방식이다.
        
        - 비대칭키 방식
            
            사용자와 서버가 서로의 정체를 증명해야 한다.
            이 시점에서 사용되는 것이 비대칭키 방식으로 서버 또는 사용자가 Key pair를 생성한다.
            
            키 페어는 공개 키와 개인 키로 이루어진 한 쌍을 뜻하며, 공개 키는 `.pub`, 개인 키는 `.pem`의 파일 형식을 가진다.
            
            예시) 사용자가 키 페이를 생성하는 경우, 공개 키를 서버에 전송한다. 서버는 공개키를 받아서 해당 공개 키로 랜덤 값을 생성하고 해당 값은 사용자가 올바른 키 페어를 가지고 있는 지 확인하는 자물쇠와 같다.
            
            자물쇠를 받은 사용자는 개인 키로 해당 좌물쇠를 연다. 공개 키와 개인 키는 한 쌍이기 때문에 생성된 자물쇠도 개인 키로만 열 수 있다.
            
            해당 자물쇠를 열어서 나온 값을 다시 서버에 전송하고, 서버는 해당 값을 자신이 처음 보낸 값과 비교한다.
            
            두 값이 같으면, 서버는 자신의 키에 대응하는 올바른 개인 키를 보유하고 있으니 유효한 사용자로 판단하고 접속을 허용한다.
            
            이렇게 최초 접속 시 서버 간의 인증 절차가 비대칭키 방식을 통해 완료된다.
            
        - 대칭키 방식
            
            서로가 누구인지 알았으니, 이제 정보를 주고 받을 차례이다.
            보안을 위해 주고 받는 정보를 암호화 하는데, 여기서 사용하는 과정이 대칭키 방식이다.
            
            대칭키는 비대칭키와 달리 한 개의 키만 사용하고 그 때문에 ‘대칭키’라 불린다.
            
            예시) 사용자 또는 서버가 하나의 대칭 키를 만들어 공유한다.
            공유된 대칭 키를 이용해 정보를 암호화하면, 받은 쪽에서 동일한 대칭 키로 암호를 풀어 정보를 받는다. 
            정보 교환이 완료되면 해당 대칭 키는 폐기되고, 재 접속 시 마다 새로운 대칭 키를 생성하게 된다.
            
    - 사용 방법
        - SSH Key 만들기
            
            ```cpp
            $ ssh-keygen -t rsa
            // -t 옵션으로 어떤 타입의 암호화 방식을 사용할 지 선택할 수 있다.
            // 기본 값은 rsa
            
            // mac 기준, id_rsa가 개인 키, id_rsa.pub가 공개 키이다.
            // 접속하고자 하는 호스트에 공개 키를 등록하면 SSH로 접근할 때, 개인 키와 비교하여 인증
            
            ssh -p 1024 X.org
            // -p 옵션으로 포트번호를 지정할 수 있다.
            ```
            
- UFW
    - Firewall(방화벽)
        
        방화벽은 미리 정의된 보안 규칙에 기반한, 들어오고 나가는 네트워크 트래픽을 모니터링하고 제어하는 네트워크 보안 시스템이다.
        
        방화벽은 신뢰할 수 있는 내부 네트워크, 신뢰할 수 없는 외부 네트워크 간의 장벽을 구성한다.
        
        서로 다른 네트워크를 지나는 데이터를 허용 또는 거부 하거나 검열 또는 수정하는 하드웨어 또는 소프트웨어다.
        
    - Uncomplicated Firewall의 약자
        
        Debian 계열 및 다양한 리눅스 환경에서 작동되는 사용하기 쉬운 방화벽 관리 프로그램
        
        UTF는 손쉬운 조작으로 iptable 및 사슬 설정을 대신해준다.(Uncomplicated: 복잡하지 않은)
        `데비안의 기본 방화벽은 iptable이다.`
        
    - 사용 방식
        
        `ufw enable`: 방화벽 활성화
        
        `ufw status`: 방화벽 상태를 확인
        
        `ufw delete (규칙 번호)`: 정의된 특정 번호의 규칙 제거
        
        `ufw allow (포트넘버)`: 특정 포트넘버 접속 허용
        
        `ufw deny (포트넘버)`: 특정 포트넘버 접속 제한
        
- DNF
    
    `RPM` 기반 리눅스 배포판에서 사용하는 패키지 관리도구
    
- sudo
    - Super User Do(또는 Substitute User Do)의 줄임말
        - 각종 명령어 앞에 sudo를 붙이면 해당 명령어는 root 권한(최고 관리자 권한)으로 실행된다.
            
            관리자 계정 비밀번호로 로그인하는 su와 달리 sudo를 사용하는 당사자의 비밀번호를 사용한다.
            
        - sudo (명령어)
            
            일반 유저가 root 권한으로 명령을 실행
            
        - su (계정명)
            
            현재 유저를 로그아웃 하지 않은 상태로 다른 사용자 계정으로 전환
            
        - su - (계정명)
            
            다른 사용자의 계정으로 완전히 전환하고, 전환한 사용자의 환경설정을 불러옴
            
    - 사용 이유
        - root
            
            리눅스나 macOS와 같은 유닉스 계열의 운영체제에서 모든 권한을 가지고 있는 최고 관리자가 사용하는 ID를 의미하며, 최고 관리자인 사람 자체를 가리키기도 한다. User ID 번호는 0번. 유닉스 계열의 모든 운영체제에는 이 root 유저가 존재한다. macOS, 우분투처럼 root 계정을 기본 상태에서 사용할 수 없게 만든 경우라도 별도 옵션을 통해 활성화할 수 있으며, 유닉스 계열 OS에 root 계정이 없는 경우는 절대로 없다.
            
        - 최고 관리자(root)의 권한은 절대적이기 때문에, 운영체제의 모든 것을 제어할 권리를 가진다.
            
            일반적으로 유저의 계정은 root보다 권한이 낮은 일반 사용자로 만들어지기 때문에, 시스템 관리 작업 등을 할 때 sudo 라는 명령을 사용하여 임시 root 권한을 얻는다.
            
        - sudo에 명령어 대신 쉘을 넣으면 루트 쉘로 진입하게 되는데, 이 루트쉘을 띄우는 것이 해커들의 궁극적인 목표이다.
            
            루트 쉘에서 실행하는 모든 명령을 컴퓨터는 절대복종한다.
            
    - su 대비 sudo의 장점
        - root password를 효율적으로 관리할 수 있다.(왜?)
        - 여러 사람이 root 패스워드를 공유하면, 정기적인 변경의 어려움과 외부 노출확률이 높아진다.
        - log 추적이 쉬워진다.(su root의 경우 로그 확인이 안된다.)
        - 침입 탐지가 가능하다.
            
            ps 또는 w 명령어로 시스템에 root shell이 실행되어 있다면 침입을 감지할 수 있다.
            시스템 침입자는 sudo를 사용할 수 없다.
            
        
- TTY
    
    우리가 사용하는 리눅스 환경은 TTY(Teletypewriter) 위에 그려져있다.
    데스크탑 gui(xwindows) 환경은 실질적으로 콘솔 위에 올려져 있는 것이다.
    콘솔은 CLI 혹은 CUI라고 불리며 컴퓨터를 운용하기 위한 목적으로 테스트를 사용자와 주고 받는 방식의 인터페이스를 말한다.
    
    정확히 말하자면 xwindow 환경에서 작동하는 콘솔은 pts/1에 올려져 있다.
    
    전체 콘솔은 아래와 같은 구성을 가지고 있다.
    
    ```cpp
    /dev (device)
    	- TTY (일반 CLI 콘솔)
    		- TTYs (시리얼 tty)
    		- PTS (기본 xwindows를 위한 가상 콘솔)
    			- PTY (외부의 원격 접속을 위한 가상 콘솔) 
    ```
    
    - 콘솔 모드
    
    모니터, 키보드로 직접 본체에 연결된 모드를 말하고, 2번째 콘솔부터는 가상 콘솔이다.
    TTYs는 시리얼 콘솔을 의미한다.
    
    - 터미널 모드 - 본체에 LAN으로 연결된 모드를 말하며, 원격 접속을 의미한다.
        - PTY - pseudo terminal(가상 터미널)
        - PTS - 리눅스 커널 옵션에 /dev/pts 부분을 의미하고, 파일 시스템이다.
    
- cron
    - cron - daemon to execute scheduled commands
        
        (예약된 명령들을 실행하는 백그라운드 프로그램)
        
        - Daemon이란?
            
            데몬은 사용자가 직접적으로 제어하지 않고, 백그라운드에서 돌면서 여러 작업을 하는 프로그램을 말한다.
            
        - `ps -ef | grep crond` 크론 실행 확인
    - crontab - cron 작업을 설정하는 파일
        
        cron 프로세스는 `/etc/crontab` 파일에 설정된 것을 읽어 작업을 수행
        관리자가 직접 지정한 작업들을 설정하며, 임의의 사용자 권한으로 실행할 수 있다.
        시스템 관련 작업들을 등록해 사용하는 곳이다.
        
        - 설정 예제
            - 최초 실행 시, 아래 내용이 기본적으로 작성되어 있다.
                
                ![Screen Shot 2022-01-20 at 7.22.10 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-20_at_7.22.10_PM.png)
                
            - 위 사진에서 설명해주는 것과 같이 각 필드를 아래 순서로 채운다.
                - 분 (0 ~ 59)
                - 시 (0 ~ 23)
                - 일 (0 ~ 31)
                - 월 (1 ~ 12)
                - 요일 (0 ~ 7)
                - 사용자명
                - 실행할 명령.
                
                매 시 10분에 한번씩 `/(root directory)` 로 이동하는 명령은 아래와 같이 적어줄 수 있다.
                
                ![Screen Shot 2022-01-20 at 7.24.31 PM.png](Born2beroot%20afe2dccdcc2749b2b2a9418725a34bd9/Screen_Shot_2022-01-20_at_7.24.31_PM.png)
                
            - cron의 첫 5개 필드(시간)는 여러 연산자를 통해 하나 이상의 값을 포함할 수 있다.
                - `*` - 별표 연산자는 임의의 값 또는 항상을 의미한다.
                    
                    (시간 필드에 별표 기호가 있으면, 작업이 매시간 수행된다는 의미다.)
                    
                - `,` - 쉼표 연산자는 반복할 값 목록을 지정할 수 있다.
                    
                    (시간 필드에 1, 3, 5가 있는 경우, 작업은 오전 1시, 3시, 5시에 실행된다.)
                    
                - `-` - 하이픈 연산자는 값의 범위를 지정할 수 있다.
                (시간 필드에 1-5가 있는 경우, 오전 1시부터 5시까지 각 시간에 실행된다.)
                - `/` - 슬래시 연산자는 특정 간격 동안 반복될 값을 지정할 수 있다.
                (시간 필드에 `* / 4`가 있는 경우, 4시간마다 작업이 수행된다.)
            - crontab 명령어
                
                crontab 명령어를 통해 명령어를 작성할 수 있다.
                (사용자를 지정하면 저장 위치가 `/var/spool/cron` 으로 다르다.)
                
                - `crontab -l` 예약된 작업 리스트
                - `crontab -e` 예약된 작업 수정
                - `crontab -r` 예약된 작업 삭제
                - `crontab -u <유저명>` 해당 유저의 crontab 파일을 보거나 삭제, 편집 가능
                
- GRBU(부트로더)
    
    GRUB는 ‘Grand Unified Bootloader’의 약자로, GNU 하에서 개발된 멀티 부트로더이다.
    
    부트로더란 리눅스 부팅되기 전 부팅의 모든 과정을 진행하는 부팅 전문 프로그램
    
    시스템에 전원이 공급되면 ROM-BIOS에서 시스템 제어권을 가지고, 장착된 하드웨어 점검과 인식을 한다. 그 후, ROM-BIOS는 첫 번째 부트 섹터인 MBR에 있는 부트로더에게 그 제어권을 넘겨준다.
    
- apt-get
    
    데비안(Debian) 계열 리눅스에서 사용하는 패키지 관리 명령어 도구
    
    - 패키지 인덱스 정보 업데이트: `sudo apt-get update`
    - 패키지 업그레이드: `sudo apt-get upgrade`
    - 의존성 검사하며 업그레이드: `sudo apt-get dist-upgrade`
    - 패키지 설치: `sudo apt-get install`
    - 패키지 재설치: `apt-get --reinstall install (패키지)`
    - 패키지 삭제(설정 파일 제외): `sudo apt-get remove (패키지)`
    - 패키지 삭제(설정 파일 포함): `sudo apt-get --purge remove (패키지)`
    - 패키지 소스코드 다운로드: `sudo apt-get source (패키지)`
    - 소스코드에 의존성을 가지게 빌드: `sudo apt-get build-dep (패키지)`
    - 패키지 검색: `sudo apt-cache search (패키지)`
    - 패키지 정보 보기: `sudo apt-cache show (패키지)`
    
    apt를 이용해서 설치된 deb패키지는 /var/cache/apt/archive/ 에 설치된다.
    
- 포트  포워딩
    
    [포트 포워딩을 왜 하는 거야?](https://velog.io/@dha/%ED%8F%AC%ED%8A%B8-%ED%8F%AC%EC%9B%8C%EB%94%A9-%EC%99%9C-%ED%95%98%EB%8A%94-%EA%B1%B8%EA%B9%8C)
    
- Port
    - Port
        
        TCP 또는 UDP에서 어플리케이션이 상호 구분을 위해 사용하는 번호이다.
        쉡게 말하면, 각 프로토콜의 데이터가 통하는 논리적 통로이다.
        
        예를 들어 하나의 서버가 있을 때, 서버가 다양한 역할을 하는 경우가 있다.
        웹 사이트를 전달해주는 역할, 파일을 요청하는 역할이 있다고 가정하고 클라이언트가 서버에 요청을 보냈을 때, 서버는 해당 요청이 사이트 요청인지, 파일 요청인지 구분할 수 있는 방법이 필요하게 된다.
        이 때, Port를 사용하게 된다.
        
    - Port number
        
        포트는 숫자로 표현하게 되어 있으며, 0 ~ 65535번까지 존재하며 아래와 같이 구분된다.
        
        - 잘 알려진 포트(well-known port) - 0 ~ 1023 / 국제 도메인 관리기구에서 통제
            - [FTP](https://namu.wiki/w/FTP) - 20, 21 (TCP)
            - [SSH](https://namu.wiki/w/Secure%20Shell) - 22 (TCP)
            - [텔넷](https://namu.wiki/w/%ED%85%94%EB%84%B7) - 23 (TCP)
            - [SMTP](https://namu.wiki/w/SMTP) - 25 (TCP)
            - [DNS](https://namu.wiki/w/DNS) - 53 (TCP/UDP)
            - [DHCP](https://namu.wiki/w/DHCP) - 67 (UDP)
            - [HTTP](https://namu.wiki/w/HTTP) - 80 (TCP)
            - [HTTPS](https://namu.wiki/w/TLS) - 443 (TCP)
            - RDP - 3389 (TCP/UDP)
        - 등록 포트 - 1024 ~ 49151 / 국제 도메인 관리기구에 등록
        - 동적 포트 - 49152 - 65535 / 임시 포트, 어떤 프로세스든 임의로 사용 가능
    
- 논리 프로세서
    - 우리는 일반적으로 `processor 0 ~ n` 이라고 할 때, 실제 CPU 개수를 n개라고 생각하지만, 이는 틀렸다.
        
        일반적으로 CPU는 다수의 코어를 가지고, 인텔 하이퍼-스레딩 기술을 통해 논리적으로 CPU 개수를 두배로 늘린다.
        
        그래서 일반적으로 `논리 프로세서 개수 = 물리 CPU 개수 * CPU 별 코어 개수 * 2` 라고 생각할 수 있다.
        
        (하지만, 하이퍼 스레딩을 지원하지 않는 경우 `논리 프로세서 개수 = 물리 CPU 개수 * CPU 별 코어 개수` 가 된다.)
        
- Kernel
    
    커널은 운영체제의 심장이자 운영체제를 규정짓는 매우 중요한 부분이다.
    
    하드웨어의 자원을 자원이 필요한 프로세스에 나눠주고, 프로세스 제어, 메모리 제어, 프로그램이 요구하는 시스템 콜 등을 수행하는 부분으로 운영체제 최 하단부에서 돌아간다.
    
    현재 대부분의 OS는 커널 위에 여러가지 레이어를 올린 것으로 커널에 문제가 생기면 운영체제를 못쓰게 된다.
    
    페도라, 데비안, 우분투 등의 운영체제가 리눅스로 묶이는 것도, 리눅스 커널을 사용하기 때문이다.
    

## 참고자료

[Git - 프로토콜](https://git-scm.com/book/ko/v2/Git-%EC%84%9C%EB%B2%84-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C)

[Difference between ESTABLISHED and LISTENING](https://askubuntu.com/questions/854354/difference-between-established-and-listening)

[How do I check whether I am using LVM?](https://askubuntu.com/questions/202613/how-do-i-check-whether-i-am-using-lvm)

[How to restrict awk math output to 2 decimal places](https://unix.stackexchange.com/questions/496906/how-to-restrict-awk-math-output-to-2-decimal-places)

[How to View the Physical CPU, Logical CPU and CPU Number of Linux Servers - Develop Paper](https://developpaper.com/how-to-view-the-physical-cpu-logical-cpu-and-cpu-number-of-linux-servers/)

[Linux : Crontab으로 Cron Jobs 스케쥴링 방법, 예제, 명령어](https://jjeongil.tistory.com/1455)

[How to enforce password complexity on Linux](https://www.networkworld.com/article/2726217/how-to-enforce-password-complexity-on-linux.html)

[](https://www.technipages.com/linux-configure-default-password-aging-settings-new-accounts)

[포트 포워딩이란?](https://lamanus.kr/59)

[](https://zetawiki.com/wiki//etc/network/interfaces)

[파일 암호화의 모든 것](https://zdnet.co.kr/view/?no=20141215091830)

[[unix 시스템 기초] 리눅스 의 기초 이론인 TTY와 PTS, PTY에 대해서 알아보자.](https://cosmosproject2015.tistory.com/143)

[리눅스 서버를 다루는 기술: 초보 시스템 관리자의 일기 | 우분투 방화벽 ufw로 시스템 보호하기](https://thebook.io/006718/part02/ch05/06/)

[가비아 라이브러리](https://library.gabia.com/contents/infrahosting/9002/)

[OpenSSH: Manual Pages](https://www.openssh.com/manual.html)

[What is APT and Aptitude? and What's real Difference Between Them?](https://www.tecmint.com/difference-between-apt-and-aptitude/)

[](https://github.com/chichoon/subject_ko/blob/born2beroot/born2beroot/born2beroot_ko.md)

[접근 통제(Access Control) 와 DAC/MAC](https://www.lesstif.com/ws/access-control-dac-mac-43843837.html)

[born2beroot 아카이브 (배포판)](https://parkseunghan.notion.site/born2beroot-afdb78d74995456d9c91a4ae1be9874f)
