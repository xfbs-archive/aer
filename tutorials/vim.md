# Vim einrichten für Bluespec

Es ist natürlich ziemlich doof, wenn man kein Syntax-Highlighting hat beim Programmieren. Es ist zwar nicht unbeding notwendig, aber es fühlt sich einfach besser an. Zum Glück gibt es *den einen Editor*, der für alles Plugins hat. Ich rede natürlich über Vim. 

Aber wie richtet man das eigentlich ein, zum Beispiel auf dem RBG-Pool? Das geht relativ einfach, in drei Schritten. 

1.  [Pathogen](https://github.com/tpope/vim-pathogen) installieren. Warum? Pathogen ist ein Plugin-Manager, der einfach alle Plugins lädt, die du in den Ordner `~/.vim/bundle` packst. 

    mkdir -p .vim/autoload .vim/bundle
    curl -LSs https://tpo.pe/pathogen.vim > .vim/autoload/pathogen.vim
    cat "execute pathogen#infect()" > .vimrc

2.  [Vim Sensible](https://github.com/tpope/vim-sensible) installieren. Danke Tim!

    git clone https://github.com/tpope/vim-sensible ~/.vim/bundle/vim-sensible

3.  [Vim BSV](https://github.com/mtikekar/vim-bsv) installieren. 

    git clone https://github.com/mtikekar/vim-bsv ~/.vim/bundle/vim-bsv

Fertig! Hier noch ein Video:

[![asciicast](https://asciinema.org/a/O4UQ9stft1G0QagvCsOM7taKv.png)](https://asciinema.org/a/O4UQ9stft1G0QagvCsOM7taKv)
