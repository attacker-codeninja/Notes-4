# Password Reset
  - Include email as second parameter and you might get the token sent to you too
  - Try to use personnal reset token on victim's account
  - change host header to hacker.com and token might be sent with hacker.com?token=... instead of website.com?token=...
  - How are token are generated ? Timestamp, id of user, email of user ...
  - Add a cc to the victim's email (victim@mail.ltd%0a%0dcc:hacker@mail.ltd) 

  - manipulate token response : 
    - remove token
    - 00000000
    -  null/nil
    -  expired token
    -  array
    -  change 1 character
    -  unicode jutzu (with punycoder) 
    -  race conditions
