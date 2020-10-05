FROM quay.io/operator-framework/ansible-operator
RUN ansible-galaxy install nikhilk.hello_world_k8s

COPY . ${HOME}/roles/hello-world-k8s
COPY watches.yaml ${HOME}/watches.yaml

RUN echo $'--- \n\
 - version: v1alpha1\n\
 group: examples.nikhilk.io\n\
 kind: HelloWorld\n\
 role: /opt/ansible/roles/nikhilk.hello_world_k8s' > ${HOME}/watches.yaml
