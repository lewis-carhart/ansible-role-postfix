# ansible-role-postfix
 An Ansible Role for setting up Postfix

 ## Variables

 Here is an example variables file

 ```
 ---
   postfix:
     main:
       soft_bounce: "no"
       queue_directory: /var/spool/postfix
       command_directory: /usr/sbin
     master:
       - service: slow
         type: unix
         private: -
         unpriv: -
       - service: email_rescue_processor
         type:
         private: -
         unpriv:
         args:
           - content_filter:
           -
     header_checks:
       feedback_id: WARN
       priority_server: 10.0.1.16

 ```

 ## Handlers

 This role provides three handlers

 * start-postfix
 * reload-postfix
 * check-postfix

 ## Example Task with role

 ```
 ---

 ```
