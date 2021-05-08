GitHub repository : <https://github.com/Choi-Dohyon/SSU>

# Git과 GitHub 사용하기

Git과 GitHub를 사용하기 위해서는 다음 두 작업을 먼저 진행해야 합니다.  

> </br>
>
> * GitHub 회원가입하기
>
> </br>
>
> * Git 설치하기(GitBash)
>
> </br>

</br>

GitHub 링크 : <https://github.com/>  
GitBash 다운로드 : <https://git-scm.com/downloads>

---

## GitHub repository 생성하기

</br>

![pic1](https://user-images.githubusercontent.com/65977106/117539324-19fa5400-b045-11eb-8dee-a2d165476687.png)

---

## 로컬 저장소 설정

</br>

먼저 로컬 저장소로 선택할 폴더를 하나 만들고 우클릭을 한 뒤 'Git Bash Here'을 눌러줍니다.

![pic2](https://user-images.githubusercontent.com/65977106/117533662-f1646100-b028-11eb-9524-90ab07c4da0f.png)

그러면 Git 명령어를 칠 수 있는 콘솔이 나옵니다.

다음 명령어를 입력해주세요.

    git init

그리고 GitHub에서 사진 부분에 보이는 주소를 복사해주세요.

이 주소는 로컬저장소와 원격저장소를 연결하기 위한 명령어를 입력할 때 사용됩니다.

![pic2](https://user-images.githubusercontent.com/65977106/117539440-9f7e0400-b045-11eb-8fdd-a2c1fc393ec2.png)

다시 콘솔로 돌아와서 다음 명령어를 입력합니다. (붙여넣기 단축키는 Shift+Ins)

    git remote add origin 원격저장소주소

origin에는 원격저장소의 주소가 저장됩니다.

---

## 사용자 정보 설정  

누가 어떤 작업을 수행했는지를 알 수 있게하기 위해 다음 정보들을 입력해서 사용합니다.

    git config user.email "이메일주소"  
    
    git config user.name "이름"

정보가 잘 입력됐는지 확인하고 싶다면 뒤에 "" 부분을 생략하고 적으면 됩니다.

    git config user.email
    
    git config user.name

---

## 프로젝트 시작하기

자신이 원하는 프로젝트를 위한 파일을 로컬저장소에 생성해주세요.

여기서는 **\"Markdown을 사용한 Markdown 튜토리얼 만들기"** 를 프로젝트로 설정해보겠습니다.

저는 확장자가 md인 tutorial이라는 빈 파일을 만들었습니다.

---

## 파일 상태 확인하기  

git은 프로젝트를 진행하면서 파일들의 상태가 수시로 바뀝니다.

파일들의 상태를 확인하기 위해서 다음 명령어를 사용합니다.

    git status

    git status -s

그러면 사진과 같이 나오게 됩니다.

![pic3](https://user-images.githubusercontent.com/65977106/117539502-f1bf2500-b045-11eb-9d0c-5e150f5792f5.png)

-s 옵션이 붙은 경우 간단한 문자들로 현재 파일의 상태를 확인할 수 있습니다.

-s 옵션을 붙이지 않고 `git status` 명령어를 사용하면 현재 파일이 Untracked 하다고 되어있을 것입니다.

즉, 현재 이 파일은 Git에서 관리하고 있지 않다는 뜻입니다.

---

## add와 commit

</br>

이제 파일에 작업을 해봅시다.

저는 간단하게 제목과 목차를 적고, 파일을 저장했습니다.

이제 파일을 준비영역(Staging Area)으로 옮기기 위해 add 명령어를 사용해 보겠습니다.

    git add 파일명

    git add .

특정 파일 하나만을 준비영역으로 옮기고 싶다면 `git add 파일명`을 쓰면 됩니다.

`git add .`는 준비영역으로 옮길 수 있는 모든 파일들을 add 해주니까 상황에 따라 사용하면 됩니다.

</br>

다시 `git status` 명령어를 사용해주세요.

![pic4](https://user-images.githubusercontent.com/65977106/117539691-ba9d4380-b046-11eb-8efb-59960ec7f942.png)

그러면 사진과 같이 tutorial.md가 수정되었다는 문구가 나옵니다.

지금은 Git에서 tutorial.md라는 파일을 관리하고 있다는 뜻이 됩니다.

</br>

add를 사용한 다음 지금의 파일의 변경사항을 저장하려면 다음 명령어를 입력합니다.

    git commit -m "메세지"

![pic5](https://user-images.githubusercontent.com/65977106/117539787-1b2c8080-b047-11eb-8a91-f66085688e5a.png)

이 명령어를 사용하고 나면 몇개의 파일이 어느정도 바뀌었는지를 간단하게 알려줍니다.

---

## push

이제 GitHub에 commit된 내용을 올려봅시다.

    git push origin 브랜치명

현재는 master에서 작업을 하고 있었으니 `git push origin master`이라고 입력하면 되겠습니다.

![pic6](https://user-images.githubusercontent.com/65977106/117539883-8413f880-b047-11eb-8ca9-1dcca99fdc22.png)

이제 GitHub에 가면 로컬 저장소에 있는 파일이 이 곳에도 저장이 된 것을 확인할 수 있습니다.

그리고 commit history 역시 원격저장소(GitHub)에서 확인할 수 있습니다.

브랜치에 대한 자세한 내용은 바로 다음 부분에서 나옵니다.

---

## 브랜치

</br>

우리는 지금 master라는 브랜치에서 작업을 하고 있습니다.

하지만 master 브랜치에서만 작업을 하면 버전을 관리하기 어렵습니다.

그래서 대부분은 다른 브랜치를 만들어서 그 곳에서 오류를 수정하거나 기능을 추가하는 방식을 취합니다.

그리고 브랜치를 병합시켜서 작업물을 완성합니다.

현재 제가 작업하고 있는 tutorial 파일은 제목과 목차만 존재하고, 본문은 존재하지 않습니다.

저는 브랜치를 만들어서 그 브랜치 안에서 본문을 작성하려고 합니다.

</br>

먼저, 브랜치를 추가하는 명령어부터 알아봅시다.

    git branch 브랜치명

브랜치가 잘 만들어졌는 지 확인해보려면

    git branch

라고 입력하면 다음과 같이 브랜치들을 확인할 수 있습니다.

![pic7](https://user-images.githubusercontent.com/65977106/117540143-a9edcd00-b048-11eb-94dd-e71b30c3aea7.png)

브랜치가 잘 만들어졌으면 해당 브랜치로 이동해서 이전에 작업하던 방식처럼 작업해주면 됩니다.

    git checkout 브랜치명

**Branch_A**에서는 본문 1~6번을 작성할 것이고,

**Branch_B**에서는 본문 7~13번을 작성할 것입니다.

</br>

해당 브랜치에서의 작업이 끝났다면 merge 명령어를 사용해 master 브랜치를 병합하는 작업을 해보겠습니다.

먼저, `git checkout master`을 사용해서 master 브랜치로 이동한 후 다음 명령어를 사용합니다.

![pic8](https://user-images.githubusercontent.com/65977106/117540981-b411ca80-b04c-11eb-820a-546a108035a2.png)

    git merge 브랜치명

![pic9](https://user-images.githubusercontent.com/65977106/117541017-d9063d80-b04c-11eb-8e4b-973ee76dea4f.png)

Branch_B에 대해서도 똑같이 병합하면 됩니다.

Branch_B를 작업하는 중간에 master에서 수정이 이루어졌더라도 병합이 가능합니다.

**단, 서로 같은 부분을 수정했다면 충돌이 일어나니 주의해야합니다.**

이제 본문은 전부 완성이 되었습니다.

그런데 수정하고 싶은 부분이 있어서 Branch_C에서 추가 작업을 하려고 합니다.

이 과정에서 3번의 commit이 일어났고, 이 중 2번째 commit이 마음에 들어 이때로 돌아가려고 합니다.

먼저, commit 기록을 보는 법은 log 명령어를 사용합니다.

    git log

![pic10](https://user-images.githubusercontent.com/65977106/117541341-65fdc680-b04e-11eb-9f1e-80bfa9926d40.png)

특정 commit으로 돌아가면서 특정 commit 이후의 commit은 삭제하려면 다음 명령어를 사용합니다.

    git reset --hard HEAD^

    git reset --hard HEAD~숫자

`git reset --hard HEAD^`의 경우는 바로 이전의 commit으로 돌아가고,

`git reset --hard HEAD~숫자`의 경우 숫자에 적은 만큼의 이전 commit으로 돌아가게 됩니다.

저는 `git reset --hard HEAD^`을 사용해보겠습니다.

![pic11](https://user-images.githubusercontent.com/65977106/117541418-bd9c3200-b04e-11eb-8b12-a270594d2dc3.png)

그러면 가장 최근 commit이 바뀐 것을 확인할 수 있습니다.

</br>

또, 브랜치작업이 끝났으니 master와 병합을 하려고 합니다.

이번에는 merge가 아닌 rebase를 사용하려고 합니다.

    git rebase 브랜치명

![pic12](https://user-images.githubusercontent.com/65977106/117541544-52069480-b04f-11eb-9587-183122f3b35e.png)

그리고 다시 master로 이동한 다음, 다시 rebase를 사용해줍니다.

![pic13](https://user-images.githubusercontent.com/65977106/117541608-9eea6b00-b04f-11eb-85fd-7c5952189cd9.png)

rebase는 merge보다 commit history가 더 깔끔하다는 장점이 있습니다.

---

## GitHub에서 데이터 받아오기

이번에는 github에 있는 파일을 가져와서 작업하는 방법에 대한 설명입니다.

다른 사람이 작업하고 있었던 파일을 가져와서 내가 작업하고 싶은 경우 등에 사용할 수 있겠습니다.

    git pull origin 브랜치명

지금 쓰고 있는 이 README 파일을 GitHub에 가서 직접 업로드 한 뒤에 로컬 저장소로 가져와보겠습니다.

![pic14](https://user-images.githubusercontent.com/65977106/117541921-313f3e80-b051-11eb-81d4-35005154549d.png)

</br>

다른 프로젝트에 처음 참여하거나 아예 저장소를 복제하고 싶다면 clone 명령어를 사용하면 됩니다.

    git clone 원격저장소주소

이 명령어를 실행하면 프로젝트 히스토리를 전부 가져오게 됩니다.

---

## tag 달기

</br>

이제 commit을 하고, push를 하기 전에 tag를 달아보려 합니다.

tag는 보통 프로젝트의 버전을 표시하기 위해 사용합니다.

    git tag 태그명

tag를 단 후에 push를 하게 되면 다음과 같이 GitHub에서도 tag를 확인할 수 있습니다.

</br>
