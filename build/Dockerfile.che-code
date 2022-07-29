FROM quay.io/che-incubator/che-code:insiders

USER root

RUN mkdir /checode-extensions

RUN /checode-linux-libc/bin/che-code --extensions-dir /checode-extensions \
      --install-extension ms-python.python \
      --install-extension vscode.npm \
      --install-extension redhat.vscode-yaml \
      --install-extension esbenp.prettier-vscode \
      --install-extension dbaeumer.vscode-eslint \
      --install-extension ms-toolsai.jupyter \
      --install-extension ms-toolsai.jupyter-keymap \
      --install-extension ms-toolsai.jupyter-renderers \
      --install-extension vscode.json-language-features \
      --install-extension eamodio.gitlens \
      --install-extension redhat.java \
      --install-extension golang.Go \
      --install-extension ms-azuretools.vscode-docker \
      --install-extension redhat.vscode-xml \
      --install-extension hashicorp.terraform \
      --install-extension dsznajder.es7-react-js-snippets \
      --install-extension GitLab.gitlab-workflow \
      --install-extension rust-lang.rust \
      --install-extension ms-kubernetes-tools.vscode-kubernetes-tools \
      --install-extension batisteo.vscode-django \
      --install-extension emmanuelbeziat.vscode-great-icons \
      --install-extension humao.rest-client \
      --install-extension redhat.vscode-openshift-connector \
      --install-extension redhat.vscode-tekton-pipelines \
      --install-extension redhat.vscode-xml

COPY entrypoint-init-container.sh /

RUN chmod +x /entrypoint-init-container.sh

RUN sed -i 's/https:\/\/open-vsx.org\/vscode\/gallery//g' checode-linux-libc/product.json && \
    sed -i 's/https:\/\/open-vsx.org\/vscode\/item//g' checode-linux-libc/product.json

RUN sed -i 's/https:\/\/open-vsx.org\/vscode\/gallery//g' checode-linux-musl/product.json && \
    sed -i 's/https:\/\/open-vsx.org\/vscode\/item//g' checode-linux-musl/product.json
    
USER 1001
