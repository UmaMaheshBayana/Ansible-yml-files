---
- name: Install Nginx on the Web Machine
  hosts: app-machine01
  become: yes
  tasks:
   - name: install epel
     yum:
       name: epel-release
       state: present
   - name: INstall nginx packeges
     yum:
       name: nginx
       state: present
       update_cache: yes
   - name: Start nginx
     service:
       name: nginx
       state: started
       enabled: yes
