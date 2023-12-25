#git 

- git 폴더가 있는 같은 선상에 `.gitignore` 파일을 생성한다.

```git
## 파일 무시
test.txt

## 다음과 같은 확장자는 전체 무시
*.text
*.exe
*.zip

## 폴더 무시
test/
```

>[!note] .gitignore 파일에서 **# 뒤에 쓰는 내용은 주석**처리 된다.

.gitignore 파일을 작성 후 add > commit > push 까지 해야 ignore 가 적용된다.

```shell
$ git add .
$ git commit -m "ignore file&folder config"
$ git push origin master
```

>[!danger] 기존의 git관리를 받고 있던(commit된 것들) 파일이나 폴더를 .ignore파일에 작성하고 add>commit>push 해도 ignore되지 않는다. 이럴 때는 기존에 가지고 있는 cached를 지워야 한다.

```shell
## 파일 이라면
git rm --cached test.txt

## 전체파일 이라면
git rm --cached *.txt

## 폴더 라면
git rm --cached test/ -r
```

### git rm --cache
Staging Area(add를 하고 나서의 영역)에서 파일을 제거하고 working directory(Local)에서는 파일을 유지하는 명령어. 위의 명령어를 실행한 후 꼭 commit을 해줘야 한다.

# 참고
https://kcmschool.com/194