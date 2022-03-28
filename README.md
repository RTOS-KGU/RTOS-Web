# RTOS-Web

RTOS-Web site hugo repository입니다.  
기본적으로 markdown 파일을 content 폴더에 넣어 포스팅하는 형식으로 이루어져있습니다.  

## Theme  

Theme는 Hugo의 hugo-book을 사용했습니다.  
(https://github.com/alex-shpak/hugo-book)  

## 서버 재부팅 및 실행  

```bash
$ sudo reboot

$ cd /home/rtos/rtos_web/

$ echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.zshrc

$ source ~/.zshrc

$ nohup hugo server --bind=203.249.22.240 --port=8080 &
```

## To-DO

- [ ] 프로세스 벡그라운드 실행을 nohup으로 하고있는데 tmux로 바꾸어 사용  
- [ ] 홈 디렉토리 위치를 /home/rtos/rtos_web/으로 변경
