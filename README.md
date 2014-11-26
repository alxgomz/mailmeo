mailmeo
=======

MailMeo is an attempt to provide a scalable, easy to deploy, feature rich and original mail system.
At the moment, Mailmeo is only targeted to Debian system.
I wanted to try something else than the usual postfix + courrier or cyrus that can be found all around the web.
For that reason, mailmeo uses Exim4 as an MTA and dovecot as a POP/IMAP server (not exactly exotic but honestly... who can compete with Dovecot?).
This is a work in progress, and at the moment only an partial ansible playbook is published.

I wrote an howto few years ago about to to set it up (it's now most definitely outdated):

http://www.howtoforge.com/setting-up-a-mail-server-using-exim4-clamav-dovecot-spamassassin-and-many-more-on-debian

With that repo, I hope to build packages and ansble playbooks to make it very easy to deploy.

Right now the only role(s) provided by the playbook is:

 - OpenLDAP server (with automatic multi-master deployment)

To launch deployment, fill the invenory file (ansible/etc/hosts) with the server names (only FQDN are supported)

    ~$ ansible-playbook -u root -i etc/hosts mailmeo.yaml
