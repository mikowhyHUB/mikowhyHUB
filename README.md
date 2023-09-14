# Welcome to my GitHub profile👋
![](https://github.com/mikowhyHUB/mikowhyHUB/blob/main/ms_banner.png?raw=true)

My name is Mikołaj and I'm a self-taught programmer with a passion for Python. I've been able to develop strong programming skills through self-study and mentorship. I'm an active member of the Hackerspace Trojmiasto community, where I continue to learn and work on projects that challenge and expand my skills.

📚 Currently I'm learning Django

### Some of my projects:
- [Tram Information for Hackerspace Trójmiasto](https://github.com/mikowhyHUB/hs3-traminformation)
- [Caesar Cipher Project](https://github.com/mikowhyHUB/caesar-cipher)
- [Movie ratings](https://github.com/mikowhyHUB/movie-ratings)



# Contact me
Mail: mikolaj.kalisz@gmail.com 

Discord: MIKOWHY#1860

[<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40'>](https://github.com/mikowhyHUB)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/linkedin.svg' alt='linkedin' height='40'>](https://www.linkedin.com/in/mikobczak/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/twitter.svg' alt='twitter' height='40'>](https://twitter.com/_mikowhy)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/reddit.svg' alt='Reddit' height='40'>](https://www.reddit.com/user/_mikowhy)  

![Profile views](https://gpvc.arturio.dev/mikowhyHUB)  

# Jak zacząć używać konfiguracji NeoVim
## Zanim zaczniesz konfigurować NeoVima, potrzebujesz specjalnych czcionek:
### Instalacja czcionki umożliwiającej wyświetlanie specjalnych znaków / ikon w terminalu.
Uruchom nowe okno terminala (bez logowania się na dev). Następnie:

```bash
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.0/Hack.zip
unzip Hack.zip *.ttf -d ~/.local/share/fonts
```

### Następnie należy zmienić używaną w terminalu czcionkę na tą nowo zainstalowaną. 
#### W przypadku domyślnego terminala Mint: 
Zamknij wszystkie okna terminala jakie masz włączone, włacz ponownie terminal -> Edit(Na górze po lewej stronie) -> Preferences -> zakładka Text -> zaznacz opcję "Custom font" -> wybierz z listy "Hack Nerd Font".

## Instalacja oraz konfiguracja NeoVim:

1. Zaloguj się na dev.

1. Upewnij się, że NeoVim jest zainstalowany. Aby to zrobić, spróbuj go uruchomić: `nvim`. Jeśli wyświetla się komunikat `nvim: command not found`:

    ```bash
    mkdir ~/.local/bin/
    curl -Lo ~/.local/bin/nvim https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
    chmod u+x ~/.local/bin/nvim
    nvim
    ```

    Jeśli nadal komenda `nvim` nie działa:

    ```bash
    echo 'PATH="$HOME/.local/bin/:$PATH"' >> .bashrc
    source ~/.bashrc
    ```

1. Pobierz projekt dotfiles:

    ```bash
    setup-project.sh dotfiles@upstream/rc
    ```

1. Przejdź do pobranego repozytorium: 

    ```bash
    cd ~/projects/dotfiles
    ```

1. Upewnij się, że masz aktualną wersję konfiguracji. 

    ```bash
    git checkout rc && git pull upstream rc
    ```

1. Tylko jeśli korzystałeś wcześniej z NeoVim (w przypadku pierwszej styczności można pominąć ten krok).
    1. Stworzenie kopii aktualnej konfiguracji

    ```bash
    mv ~/.config/nvim ~/.config/nvim{,.bak}
    ```

    1. Stworzenie kopii plików tymczasowych / podręcznych NeoVim'a

    ```bash
    mv ~/.local/share/nvim{,.bak}  
    mv ~/.local/state/nvim{,.bak}  
    mv ~/.cache/nvim{,.bak}
    ```

1. Utwórz symlink do katalogu z konfiguracją

    ```bash
    ln -s ~/projects/dotfiles/nvim ~/.config/nvim
    ```

1. Uruchom NeoVim: `nvim`. Po pierwszym uruchomieniu pojawi się okno informujące, że są pobierane pluginy. Zaczekaj aż wszystkie pluginy zostaną pobrane.

Gratulacje! Od teraz `nvim` jest poprawnie skonfigurowany.
