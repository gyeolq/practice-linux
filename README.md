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
pwd # 현재 디렉토리 확인
ls # 파일 및 디렉토리 확인
cd # 디렉토리 이동
mkdir # 디렉토리 생성
touch # 파일 생성
cp # 파일 및 디렉토리 복사
mv # 파일 및 디렉토리 이동
rm # 파일 및 디렉토리 삭제
rmdir # 비어 있는 디렉토리 삭제
cat # 파일 전체 내용 확인
less # 파일 내용을 페이지 단위로 확인
head # 파일 내용을 앞부분부터 확인
tail # 파일 내용을 뒷부분부터 확인
grep # 원하는 문자열 탐색
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
```

## 명령어 사용 예시
```bash
cp a.txt b.txt
cp a.txt /
rm -rf a.txt
cat > a.txt
head -n 3 a.txt
tail -f a.txt
grep "ERROR" a.txt | tail -n 1
grep "ERROR" a.txt | wc -l
find . -name "a.txt"
echo "str" > a.txt
wc -l a.txt
sort -u a.txt
uniq -c a.txt
ls *.txt
ls a?.txt
ls a[12].txt
find . -name ".txt" -type f | xargs ls
chmod 755 a.txt
chmod u+x a.txt
chown user a.txt
```