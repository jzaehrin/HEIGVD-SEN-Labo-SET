# The Social-Engineer Toolkit (SET)

## Introduction

Selon la propre description donnée par [TrustedSec, LLC](https://www.trustedsec.com), la société de consulting américaine responsable du développement de ce produit, le [Social-Engineer Toolkit](https://github.com/trustedsec/social-engineer-toolkit/) est un framework de test d'intrusion open-source conçu pour l'ingénierie sociale. Le SET dispose d'un certain nombre de vecteurs d'attaque personnalisés qui vous permettent de réaliser rapidement une attaque crédible.

Le SET est spécifiquement conçu pour réaliser des attaques avancées contre l'élément humain. Il est rapidement devenu un outil standard dans l'arsenal des testeurs de pénétration. Les attaques intégrées dans la boîte à outils sont conçues pour être des attaques ciblées contre une personne ou une organisation utilisées lors d'un test de pénétration.


## Téléchargement et installation

Le SET est nativement supporté sur Linux et sur Mac OS X (experimental). Il est préinstallé sur Kali Linux et il est capable de se mettre à jour lui-même.

Pour une installation sur Ubuntu/Debian/Mac OS X :

```
git clone https://github.com/trustedsec/social-engineer-toolkit/ setoolkit/
cd setoolkit
pip3 install -r requirements.txt
python setup.py
```

## Que faut-il faire ?

Vous devez installer le Social Engineering Toolkit (SET), créer un collecteur d'identifiants (credential harvester), capturer certains identifiants utilisateur (les vôtres), créer une attaque de phishing, relier le collecteur d'identifiants à l'attaque. Pour chaque tâche, faites des captures d'écran de vos activités.

## Note sur l'éthique

Il n'est absolument pas acceptable d'attaquer quelqu'un pour quelque raison que ce soit. 

L'utilisation de cet outil à des fins autres que votre propre éducation et formation sans autorisation est strictement interdite par les politiques de ce cours et de l'école, ainsi que par les lois. 

Le but de cet exercice est de vous permettre de vous familiariser avec les outils et comment ils peuvent être utilisés dans le context professionnel d'un pentest. Ça vous permettra aussi de comprendre les tactiques de l'adversaire afin de pouvoir les contrer par le biais de la politique, de l'éducation et de la formation.

## Execution de SET

Pour executer SET, dans votre terminal tapper :

```
setoolkit
```

Dépendant de votre OS et de votre installation particulière, il est possible que certaines fonctionnalités ne soient pas disponibles au moins d'utiliser ```sudo```.

```
sudo setoolkit
```

# Exercice 1 - Credential Harvesting

Vous découvrirez l'un des outils les plus couramment utilisés par les ingénieurs sociaux et les acteurs malveillants pour tromper les cibles.

### Soumettre des captures d'écran

twitter.com
----
set:webattack> Enter the url to clone:twitter.com

[*] Cloning the website: http://twitter.com
[*] This could take a little bit...

The best way to use this attack is if username and password form fields are available. Regardless, this captures all POSTs on a website.
[*] The Social-Engineer Toolkit Credential Harvester Attack
[*] Credential Harvester is running on port 80
[*] Information will be displayed to you as it arrives below:
127.0.0.1 - - [12/Mar/2020 17:11:50] "GET / HTTP/1.1" 200 -
127.0.0.1 - - [12/Mar/2020 17:11:52] "GET /sw.js HTTP/1.1" 404 -
[*] WE GOT A HIT! Printing the output:
POSSIBLE USERNAME FIELD FOUND: redirect_after_login=/
PARAM: remember_me=1
PARAM: authenticity_token=2faa8c90647c11ea9ea127912f642a64
PARAM: wfa=1
PARAM: ui_metrics={"rf":{"a36a5e4cd0ce7c950adde072d6b20ee5b880b5b7c4f416145583a59eeb135183":238,"a8025fe27d3aeb7c064e4a88b16bc3bb4b45bdcecf2bbd27a1d4a8161d009eee":-111,"a2ea250455a15d8377bba40a4dc0c4345ee8153ac0340bb5cbaf2147679d5206":-1,"affe7996f317083a908cf9f424be4cf118102e81ce2082888957a5cbdcc062da":-112},"s":"MDEm84cgac2xQXk8SMNmARiuoOLDhfaRmsRN4XTb7q5Tnkl_ELfWJgKUpIwIJphia7zfhOBxs6k-BguEs_0jzy0AhiVC6Z3qtKrklXVed6KK8932N7j9wicPko9mCcxPSaIONWr_0wyQZ8qv5SR08EWyQGRW4a6hRk3ZPSqFX9P4Lcyd1ZSZZ-LS0i9oSHqGC26G83wR1ADOFc2sv7rxYbC8i4Ln24ttdDgeRUew6IFkHTl_k3gu_f7ExFDpoMJS0nl-TBdDTGzD4yALw8xZV7aDEQCh0rqwEHvhnvHykKanU9B8XgYUv_GFON5GeNdrl3kR6EWIF4yehVia3KzDcQAAAXDPhDqz"}
POSSIBLE USERNAME FIELD FOUND: session[username_or_email]=root
POSSIBLE PASSWORD FIELD FOUND: session[password]=root
[*] WHEN YOU'RE FINISHED, HIT CONTROL-C TO GENERATE A REPORT.


127.0.0.1 - - [12/Mar/2020 17:11:58] "GET /favicon.ico HTTP/1.1" 404 -
----

facebook.com
----
[*] WE GOT A HIT! Printing the output:
PARAM: jazoest=2784
PARAM: lsd=AVrYgzsZ
PARAM: display=
PARAM: enable_profile_selector=
PARAM: isprivate=
PARAM: legacy_return=0
PARAM: profile_selector_ids=
PARAM: return_session=
POSSIBLE USERNAME FIELD FOUND: skip_api_login=
PARAM: signed_next=
PARAM: trynum=1
PARAM: timezone=-60
PARAM: lgndim=eyJ3IjoxNDQwLCJoIjo5MDAsImF3IjoxNDQwLCJhaCI6ODc3LCJjIjoyNH0=
PARAM: lgnrnd=091614_0k8V
PARAM: lgnjs=1584029777
POSSIBLE USERNAME FIELD FOUND: email=root
POSSIBLE PASSWORD FIELD FOUND: pass=rootfaceook
PARAM: prefill_contact_point=root
PARAM: prefill_source=browser_onload
POSSIBLE PASSWORD FIELD FOUND: prefill_type=password
PARAM: first_prefill_source=browser_onload
PARAM: first_prefill_type=contact_point
PARAM: had_cp_prefilled=true
POSSIBLE PASSWORD FIELD FOUND: had_password_prefilled=true
PARAM: ab_test_data=AAAAAA/AfAffAfAAAAAAAAAAAAAAAAAAAAAAAAAAf/fAffAAAADAAA
[*] WHEN YOU'RE FINISHED, HIT CONTROL-C TO GENERATE A REPORT.
----

example.org
----
set:webattack> Enter the url to clone:easygateway.co

[*] Cloning the website: http://easygateway.co
[*] This could take a little bit...

The best way to use this attack is if username and password form fields are available. Regardless, this captures all POSTs on a website.
[*] The Social-Engineer Toolkit Credential Harvester Attack
[*] Credential Harvester is running on port 80
[*] Information will be displayed to you as it arrives below:
127.0.0.1 - - [12/Mar/2020 17:19:15] "GET / HTTP/1.1" 200 -
[*] WE GOT A HIT! Printing the output:
POSSIBLE USERNAME FIELD FOUND: login_username=root
POSSIBLE USERNAME FIELD FOUND: login_password=root
POSSIBLE PASSWORD FIELD FOUND: login_password=root
[*] WHEN YOU'RE FINISHED, HIT CONTROL-C TO GENERATE A REPORT.
----

Pour le collecteur d'identifiants, montrez que vous avez cloné un site en indiquant son adresse web et l'interface d'utilisateur. Saisissez les informations d'identification sur votre clone local, puis cliquez le bouton de connexion. Essayez plusieurs sites comme facebook.com, twitter.com, et d'autres qui puissent vous intéresser. Faites des captures d'écran des mots de passe collectés dans vos tests avec SET.

# Exercice 2 - Créer une attaque de phishing

Essayez la fonction d'attaque par phishing. C'est très facile à faire. Vous pouvez vous référer à ce lien pour plus d'informations http://www.computerweekly.com/tutorial/Social-Engineer-Toolkit-SET-tutorial-for-penetration-testers

----
set:phishing> Send email to:jonathan.zaehringer@heig-vd.ch

  1. Use a gmail Account for your email attack.
  2. Use your own server or open relay

set:phishing>2
set:phishing> From address (ex: moo@example.com):jonathan.zaehringer@heig-vd.ch
set:phishing> The FROM NAME the user will see:Tartempion
set:phishing> Username for open-relay [blank]:
Password for open-relay [blank]:
set:phishing> SMTP email server address (ex. smtp.youremailserveryouown.com):smtp.heig-vd.ch
set:phishing> Port number for the SMTP server [25]:
set:phishing> Flag this message/s as high priority? [yes|no]:yes
Do you want to attach a file - [y/n]: n
Do you want to attach an inline file - [y/n]: n
set:phishing> Email subject:Urgent !
set:phishing> Send the message as html or plain? 'h' or 'p' [p]:p
[!] IMPORTANT: When finished, type END (all capital) then hit {return} on a new line.
set:phishing> Enter the body of the message, type END (capitals) when finished:Bonjour,
Next line of the body:
Next line of the body: Test SEToolkit
Next line of the body:
Next line of the body: Tartempion
Next line of the body: END
----

# Exercice 3 - Explorer les liens "Phishy" et le courrier électronique "Phishy"

Pour cette dernière partie de notre exploration du phishing, nous allons utiliser un contenu réalisé par les  Dr. Matthew L. Hale, le Dr. Robin Gandhi et la Dr. Briana B. Morrison de [Nebraska GenCyber](
http://www.nebraskagencyber.com). 

Visitez : https://mlhale.github.io/nebraska-gencyber-modules/phishing/README/ et passez en revue les modules 

- Analyse d'url (ce module peut être intéressant pour vos rapports de pentest, comme outil pour sensibiliser les employés d'une entreprise, mais il risque d'être trop simple pour vous)
- Analyse d'Email (me module est probablement plus intéressant techniquement pour vous)

En général, c'est un bon exemple de matériel de formation et d'éducation qui peut aider à lutter contre les attaques de phishing et à sensibiliser le personnel d'une organisation.

Vous avez la liberté de reproduire et d'utiliser le matériel grace à sa licence.


### Soumettre des captures d'écran

Pour cette tâche, prenez des captures d'écran de :

- Vos inspections de chaque lien dans votre navigateur
- Vos inspections d'un en-tête de courrier électronique à partir de votre propre boîte de réception

