---
- name: Create a user on localhost based on user input
  hosts: localhost
  become: true
  gather_facts: false
    #vars_prompt:
    #- name: "username"
    #  prompt: "Please enter the username to create"
    #  private: no  # Set to `yes` if you want to hide input (useful for passwords)
   vars:
    username: "{{ user_name }}"

  tasks:
    - name: Check if user exists
      ansible.builtin.getent:
        database: passwd
        key: "{{ username }}"
      register: user_exists
      failed_when: false

    - name: Create the user if it doesn't exist
      ansible.builtin.user:
        name: "{{ username }}"
        state: present
        comment: "Created by Ansible playbook"
      when: user_exists.failed

    - name: Notify user of success
      debug:
        msg: "User '{{ username }}' has been created successfully!"
      when: user_exists.failed

    - name: Notify user if the user already exists
      debug:
        msg: "User '{{ username }}' already exists."
      when: not user_exists.failed

        # - name: Check if user exists
        #getent:
        # database: passwd
        # key: "{{ username }}"
        #register: user_check
        #ignore_errors: true
