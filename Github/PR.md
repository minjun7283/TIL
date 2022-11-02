# PR

PR(Pull Request)
1. Fork를 한다.

2. Fork한 저장소에서 URL을 복사
> CMD 창에 git clone (복사한)URL

3. Branch 생성
```
git chechout -b develop Switched to a new branch 'develop'
```
4. add,commit,push
```
git add
git commit -m " "
git push origin develop
```
5. Pull Request 생성
>github 저장소에서 Compare & pull request로 생성

6. 코드 변경내역을 확인하고 Merge 여부 결정
```
git pull real-blog
git branch -d develop
```