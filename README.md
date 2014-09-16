# OpenVPN-Auth-LDAP-Perl


This is a simple perl script that uses http://search.cpan.org/~chansen/Authen-Simple-LDAP-0.3/lib/Authen/Simple/LDAP.pm to do LDAP authentication for OpenVPN.

You can set your ldap settings in the auth-ldap.conf file in the same directory.  Note the conf must always be in the same directory as auth-ldap.pl as it looks in the current directory for the file.  All the options listed here http://search.cpan.org/~chansen/Authen-Simple-LDAP-0.3/lib/Authen/Simple/LDAP.pm are valid and will be passed to the constructor.

This was written as a quick workaround for the following issue in FreeBSD https://code.google.com/p/openvpn-auth-ldap/issues/detail?id=38#makechanges

Find any issues email me and I'll try to help analogrithems@gmail.com

###server.conf settings
Note inorder to use this script you must place the auth-ldap.pl & auth-ldap.conf in your openldap config directory (Usually _/etc/openvpn_).  You must also set the following in your server.conf

`
script-security 2
`

`
auth-user-pass-verify auth-ldap.pl via-file
`


###Requires
You will need to install the following perl modules

 * Authen::Simple::LDAP
 * Config::Simple

###Known Issues.
Probably doesn't support SSL or TLS as I didn't see the option in Authen::Simple::LDAP if it's critical i can probably wip it up.