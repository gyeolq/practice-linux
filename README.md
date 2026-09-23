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
```bash
whoami # 현재 사용자 표시
pwd # 현재 디렉토리 표시
ls # 파일 및 디렉토리 표시
cd # 디렉토리 이동
mkdir # 디렉토리 생성
touch # 파일 생성
cp # 파일 및 디렉토리 복사
mv # 파일 및 디렉토리 이동
rm # 파일 및 디렉토리 삭제
cat # 파일 전체 내용 표시
less # 파일 내용을 페이지 단위로 표시
head # 파일 내용을 앞부분부터 표시
tail # 파일 내용을 뒷부분부터 표시
grep # 원하는 문자열 탐색
find # 파일 및 디렉토리 검색
wc # 파일 내의 줄 수, 단어 수, 바이트, 파일명 표시
sort # 파일 내용 정렬하여 표시
uniq # 연속된 줄의 중복 제거하여 표시
chmod # 권한 변경
chmod u+x script.sh
chown # 소유자 변경
chown testuser file.log
```

## 명령어 사용 예시
```bash
ls -al
cp file1.log file2.log
cp file.log /
rm -rf file.log
cat > file.log
head -n 3 file.log
tail -f file.log
grep "ERROR" file.log | tail -n 1
grep "ERROR" file.log | wc -l
find . -name "file.log"
echo "str" > file.log
wc -l file.log
sort -u file.log
uniq -c file.log
ls *.log
ls file?.log
ls file[12].log
find . -name ".log" -type f | xargs ls
chmod 755 file.log
```