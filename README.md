# Linux(Ubuntu) 학습

## 주요 디렉토리
- `/` : Linux 파일 시스템 최상위
- `/home` : 일반 사용자 홈 디렉토리
- `/etc` : 시스템, 서비스 설정
- `/var` : 로그 등 자주 변하는 데이터
- `/tmp` : 임시 파일
- `/usr` : 프로그램 및 관련 파일
- `/opt` : 별도 애플리케이션 설치 등에 사용

## 주요 명령어
- `ls [옵션] [경로]` : 경로의 파일/디렉토리 출력
    - `-a` : 숨김 파일 포함
    - `-l` : 상세 정보 포함
- `pwd` : 현재 작업 디렉토리 출력
- `cd [디렉토리]` : 디렉토리 이동
- `mkdir [디렉토리]` : 디렉토리 생성
    - `-p` : 상위 디렉토리까지 함께 생성
- `touch [파일]` : 파일 생성
- `cp [원본] [대상]` : 파일/디렉토리 복사
    - `-r` : 재귀 복사
- `mv [원본] [대상 또는 경로]` : 파일/디렉토리 이동 또는 이름 변경
- `rmdir [디렉토리]` : 빈 디렉토리 삭제
- `rm [옵션] [파일 또는 디렉토리]` : 파일/디렉토리 삭제
    - `-r` : 재귀 삭제
    - `-f` : 확인 없이 강제 삭제
- `cat [파일]` : 파일 전체 내용 출력
- `less [파일]` : 파일 내용 페이지 단위로 출력
- `head [옵션] [파일]` : 파일 앞부분 출력
    - `-n` : n줄 출력
- `tail [옵션] [파일]` : 파일 뒷부분 출력
    - `-n` : n줄 출력
    - `-f` : 추가 내용 실시간 출력
- `echo [문자열]` : 문자열 출력
- `grep [옵션] [검색어] [파일]` : 문자 검색
    - `-i` : 대소문자 무시
- `find [검색 위치] [조건]` : 파일/디렉토리 검색
    - `-type f` : 파일 검색
    - `-type d` : 디렉토리 검색
    - `-name` : 이름 검색
- `wc [옵션] [파일]` : 줄/단어 수 출력
    - `-l` : 줄 수
    - `-w` : 단어 수
- `sort [옵션] [파일]` : 텍스트 정렬
- `uniq [옵션] [파일]` : 연속 중복 줄 제거
    - `-c` : 등장 횟수 출력
- `[명령어] | xargs [명령어]` : 앞 명령어 결과를 다음 명령어 인자로 전달
- `whoami` : 현재 사용자 출력
- `id` : 현재 사용자 UID 등 출력
- `groups [사용자]` : 사용자가 속한 그룹 출력
- `chmod [권한] [파일명]` : 파일/디렉토리 권한(rwx) 변경
    - `u` : user
    - `g` : group
    - `o` : others
    - `a` : all
- `chown [사용자] [파일]` : 파일/디렉토리 소유자 변경
- `chgrp [그룹] [파일]` : 파일/디렉토리 그룹 변경
- `ps [옵션]` : 현재 실행 중인 프로세스 출력
    - `-a` : 다른 사용자 프로세스 포함
    - `-x` : 터미널과 연결되지 않은 프로세스 포함
    - `-u` : 사용자 포함
- `top` : 실시간 프로세스/시스템 상태 출력
- `kill [PID]` : 프로세스에 signal 전달
    - `-15` : 정상 종료 요청(SIGTERM)
    -  `-9` : 강제 종료(SIGKILL)
- `jobs` : 백그라운드 작업 출력


## 치트시트
```bash
# 숨김 파일까지 포함하여 상세 정보 출력
ls -la

# 상위 디렉토리(dir1) 함께 생성
mkdir -p /dir1/dir2

# 재귀 복사
cp -r dir1 dir2

# 재귀 삭제(강제)
rm -rf dir1

# 파일 첫 n줄 출력
head -n 3 file1.txt

# 파일 추가 내용 실시간 출력
tail -f file1.txt

# 리다이렉션으로 파일에 내용 추가
echo "Hello" >> file1.txt

# 에러 검색
grep "ERROR" file1.txt

# 가장 최근 에러
grep "ERROR" file1.txt | tail -n 1

# 에러 개수
grep "ERROR" file1.txt | wc -l

# 에러를 별도 파일로 저장
grep "ERROR" file1.txt > file2.txt

# 실시간 로그에서 에러만 출력
tail -f file1.txt | grep "ERROR"

# 현재 및 하위 경로의 txt 파일 검색
find . -type f -name "*.txt"
find . -type f -name "*.txt" | xargs ls -l

# 전체 중복 집계
sort file1.txt | uniq -c

# 권한 변경
chmod 755 file1.txt
chmod u+x file1.txt

# 모든 프로세스 상세 출력
ps aux

# 프로세스 검색
ps aux | grep sleep

# 프로세스 종료
kill -15 1234
kill -15 %1
kill -9 1234

# 명령어 백그라운드 실행(&)
sleep 5 &

# 와일드카드
*.txt
file?.txt
file[12].txt
```