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
- `ls [옵션] [경로]` : 경로의 파일 및 디렉토리 출력
    - `-a` : 숨김 파일 포함
    - `-l` : 상세 정보 포함
- `pwd` : 현재 작업 디렉토리 출력
- `cd [디렉토리]` : 디렉토리 이동
- `mkdir [디렉토리]` : 디렉토리 생성
    - `-p` : 상위 디렉토리까지 함께 생성
- `touch [파일]` : 파일 생성
- `cp [원본] [대상]` : 파일 또는 디렉토리 복사
    - `-r` : 재귀 복사
- `mv [원본] [대상 또는 경로]` : 파일/디렉토리 이동 또는 이름 변경
- `rmdir [디렉토리]` : 빈 디렉토리 삭제
- `rm [옵션] [파일 또는 디렉토리]` : 파일 또는 디렉토리 삭제
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
- `find [검색 위치] [조건]` : 파일 또는 디렉토리 검색
    - `-type f` : 파일 검색
    - `-type d` : 디렉토리 검색
    - `-name` : 이름 검색


## 치트시트
```bash
# 숨김 파일까지 포함하여 상세 정보 출력
ls -la
ls *.txt
ls a?.txt
ls a[12].txt

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

# 파일에서 에러 부분 검색
grep "ERROR" file1.txt
grep "ERROR" a.txt | tail -n 1
grep "ERROR" a.txt | wc -l

# 현재 및 하위 경로의 txt 파일 검색
find . -type f -name "*.txt"
```


```bash
find # 파일 및 디렉토리 검색
wc # 파일 내의 줄 수, 단어 수, 바이트, 파일명 확인
sort # 파일 내용 정렬
uniq # 연속된 줄의 중복 제거
whoami # 현재 사용자 확인
id # 현자 사용자의 UID, GID 및 그룹 정보 확인
groups # 현재 사용자가 속한 그룹 확인
chgrp # 파일 소유 그룹 변경
chmod # 권한(rwx) 변경
chown # 파일 소유자 변경
ps # 현재 실행 중인 프로세스 확인
top # 프로세스별 실시간 CPU/메모리 사용량
jobs # 현재 쉘에서 실행 중인 백그라운드 작업 확인
kill # 프로세스에 시그널 전달
```

## 명령어 사용 예시
```bash
find . -name "a.txt"
wc -l a.txt
sort -u a.txt
uniq -c a.txt
find . -name ".txt" -type f | xargs ls
chmod 755 a.txt
chmod u+x a.txt
chown user a.txt
ps aux | grep bash
sleep 5 &
```