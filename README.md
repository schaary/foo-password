# Überschrift

## Unterüberschrift

**fett**


Das Script foo nimmt einen 32-stelligen MD5 Hash und packt und codiert diesen
so, dass der Hash als MD5-Hash für einen LDAP-Authentifizierung verwendet werden
kann.

Anwendungsbeispiel:

    Passwort: testme
    MD5-Hash: 62318aca2ef2e809a13623715a8aaff4

    Aufruf: foo 62318aca2ef2e809a13623715a8aaff4
    Ergebnis: {MD5}YjGKyi7y6AmhNiNxWoqv9A==

Damit kann ein ldif erzeugt werden

    dn: uid=nmaef,ou=ilias_ea,o=mlu,c=de
    changetype: modify
    replace: userPassword
    userPassword: {MD5}YjGKyi7y6AmhNiNxWoqv9A==

Diese LDIF-Datei kann dann in den LDAP eingespielt werden.

