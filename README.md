---
weight: 0
title: "README"
---

# RTOS-Web README

RTOS-Web site hugo repository입니다.  
기본적으로 markdown 파일을 content 폴더에 넣어 포스팅하는 형식으로 이루어져있습니다.  
https://github.com/RTOS-KGU/RTOS-Web 에도 자료를 올려두었습니다.

## Theme  

Theme는 Hugo의 hugo-book을 사용했습니다.  
(https://github.com/alex-shpak/hugo-book)  

## 서버 재부팅 및 실행  

```bash
sudo reboot

cd /home/rtos/rtos_web/

echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.zshrc (한번 했으면 다음에는 안해도 됩니다. 홈브류 환경변수 설정입니다.)

source ~/.zshrc

hugo server --bind=<서버 ip 주소> --port=8080 --renderToDisk
```

## 논문 세미나 자료 업로드  

논문 세미나 자료는 ```content/posts/``` 디렉토리에 md 형태로 올리시면 됩니다.  
위쪽의 title, date, tag, categories는 원하시는 데로 지정해주시면 됩니다.  
가능하면 이전에 포스팅한 자료 복사해서 사용해주세요.  

세미나 자료 올리실 때는 별다른 것 필요 없이 Google 프레젠테이션 -> 웹에 게시 -> 삽입 -> 게시를 누르시면 ppt에 대한 URL을 얻을 수 있는데 복사해서 만들어둔 포스팅에 붙여넣기 해주시면 됩니다. ( width="900" height="600"로 만들어주세요.)  

ex)
```html
<center>
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vQH2JmzIRFkxKg7Edq6t6vbcgmW3A-IUm3BQtqNgpsUbgi-362XspHLC-DCCGUIfFV_hHtGih1OGgb6/embed?start=false&loop=false&delayms=3000" frameborder="0" width="900" height="600" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</center>
```

## 홈페이지 수정  

기본적으로 ```content/docs/```안에 md을 넣으면 페이지가 바로 추가됩니다. ex) https://rtos.kyonggi.ac.kr/docs/members/

좌측에 메뉴로 넣고 싶으면 아래의 좌측 메뉴 수정을 따라해주시면 되고 만약에 페이지를 hidden으로 넣고 싶으시면 그냥 이 README처럼 md을 추가하시고 다른곳에서 들어갈수 있도록 만들어 주시면 됩니다.

참고로 URL로 지정될때 주소는 title로 지정되는게 아니라 md의 이름으로 지정됩니다. ex)members.md -> https://rtos.kyonggi.ac.kr/docs/members/

## 좌측 메뉴 수정

좌측 메뉴는 ```content/menu/index.md```를 수정하시면 됩니다. 메뉴에 표기되는 이름은 각 md의 title 명의 소문자로 지정됩니다.  

## Photos 사진 추가

Photos같은 경우 제가 직접 로직을 만들었는데 웹에 대한 지식이 없어서 마구잡이로 만들었습니다.. ㅎㅎ
사진을 ```static/img/portfolio```에 넣으시고 (숫자 순서대로 넣으시면 됩니다.) ```layout/shortcodes/slider.html``` 89번째 줄 for문의 i 값을 수정해 주시면 됩니다. 

## 페이지에 이미지 추가  

md에서 기본으로 불러오는 이미지 불러오기 방식을 사용하면 됩니다.  
static 폴더에 이미지를 넣으면 불러올 수 있습니다.  

```markdown
![img](/img/logo.png)

or

<img src='/img/logo.png'>
```
<img src='/img/logo.png' width="40%">  

## To-DO

- [ ] 프로세스 벡그라운드 실행을 nohup으로 하고있는데 tmux로 바꾸어 사용  
- [ ] 홈 디렉토리 위치를 /home/rtos/rtos_web/으로 변경
