FROM ocaml/opam:debian

RUN opam init && \
    # opam update && \
    opam install ocaml-lsp-server utop ocamlformat ocamlformat-rpc
    
RUN sudo apt-get install -y gdb
RUN sudo apt-get install python3
RUN code --install-extension ocamllabs.ocaml-platform && \
    code --install-extension ms-python.python

WORKDIR /workspace

RUN echo "Compiler test.c avec options et exécuter a.out : gcc -Wall -fsanitize=address test.c && ./a.out" >> /home/opam/.bashrc
RUN echo "Exécuter du code OCaml dans l'interpréteur utop : sélectionner le code puis Shift + Entrée" >> /home/opam/.bashrc
RUN echo "Compiler test.ml et exécuter : ocamlc test.ml -o test && ./test" >> /home/opam/.bashrc
