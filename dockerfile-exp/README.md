Loosly based on the excellent work of Erik Kaareng-sunde <esu@enonic.com> at enonic.

For å bygge nytt image og registrere dette i google container registry så må du enable api'et for google containers,
 deretter kan du kjøre denne kommandoen:

 gcloud container builds submit --tag gcr.io/enonic-xp-cloud/enonic-xp-image .

enonic-xp-cloud er navnet på google prosjektet.