### Select User

select UserName, UserType from User
where UserName = 'DATA'
and SHA2('DATA', 256) = PasswordHash
