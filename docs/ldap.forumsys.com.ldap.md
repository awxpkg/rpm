* ldap.forumsys.com ldap data
```
-bash-4.2# ldapsearch -W -h ldap.forumsys.com -D "uid=tesla,dc=example,dc=com" -b "dc=example,dc=com"
Enter LDAP Password:
# extended LDIF
#
# LDAPv3
# base <dc=example,dc=com> with scope subtree
# filter: (objectclass=*)
# requesting: ALL
#

# example.com
dn: dc=example,dc=com
objectClass: top
objectClass: dcObject
objectClass: organization
o: example.com
dc: example

# admin, example.com
dn: cn=admin,dc=example,dc=com
objectClass: simpleSecurityObject
objectClass: organizationalRole
cn: admin
description: LDAP administrator
<snipped>

# scientists, example.com
dn: ou=scientists,dc=example,dc=com
uniqueMember: uid=einstein,dc=example,dc=com
uniqueMember: uid=galieleo,dc=example,dc=com
uniqueMember: uid=tesla,dc=example,dc=com
uniqueMember: uid=newton,dc=example,dc=com
uniqueMember: uid=training,dc=example,dc=com
uniqueMember: uid=jmacy,dc=example,dc=com
ou: scientists
cn: Scientists
objectClass: groupOfUniqueNames
objectClass: top

# read-only-admin, example.com
dn: cn=read-only-admin,dc=example,dc=com
sn: Read Only Admin
cn: read-only-admin
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top

# italians, scientists, example.com
dn: ou=italians,ou=scientists,dc=example,dc=com
uniqueMember: uid=tesla,dc=example,dc=com
ou: italians
cn: Italians
objectClass: groupOfUniqueNames
objectClass: top

# test, example.com
dn: uid=test,dc=example,dc=com
objectClass: posixAccount
objectClass: top
objectClass: inetOrgPerson
gidNumber: 0
givenName: Test
sn: Test
displayName: Test
uid: test
initials: TS
homeDirectory: home
cn: Test
uidNumber: 24601
o: Company

# chemists, example.com
dn: ou=chemists,dc=example,dc=com
ou: chemists
objectClass: groupOfUniqueNames
objectClass: top
uniqueMember: uid=curie,dc=example,dc=com
uniqueMember: uid=boyle,dc=example,dc=com
uniqueMember: uid=nobel,dc=example,dc=com
uniqueMember: uid=pasteur,dc=example,dc=com
cn: Chemists

# curie, example.com
dn: uid=curie,dc=example,dc=com
uid: curie
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
cn: Marie Curie
sn: Curie
mail: curie@ldap.forumsys.com

# nobel, example.com
dn: uid=nobel,dc=example,dc=com
uid: nobel
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
mail: nobel@ldap.forumsys.com
sn: Nobel
cn: Alfred Nobel

# boyle, example.com
dn: uid=boyle,dc=example,dc=com
uid: boyle
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
cn: Robert Boyle
sn: Boyle
mail: boyle@ldap.forumsys.com
telephoneNumber: 999-867-5309

# pasteur, example.com
dn: uid=pasteur,dc=example,dc=com
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
sn: Pasteur
cn: Louis Pasteur
uid: pasteur
telephoneNumber: 602-214-4978
mail: pasteur@ldap.forumsys.com

# nogroup, example.com
dn: uid=nogroup,dc=example,dc=com
uid: nogroup
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
cn: No Group
mail: nogroup@ldap.forumsys.com
sn: Group

# training, example.com
dn: uid=training,dc=example,dc=com
uid: training
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
cn: FS Training
sn: training
mail: training@forumsys.com
telephoneNumber: 888-111-2222

# jmacy, example.com
dn: uid=jmacy,dc=example,dc=com
uid: jmacy
telephoneNumber: 888-111-2222
sn: training
cn: FS Training
objectClass: inetOrgPerson
objectClass: organizationalPerson
objectClass: person
objectClass: top
mail: jmacy-training@forumsys.com

# search result
search: 2
result: 0 Success

# numResponses: 24
# numEntries: 23
-bash-4.2#

```
