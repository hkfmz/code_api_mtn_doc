
# GUIDE D’UTILISATION API SMS MTN

## Usage

Pour utiliser l'API SMS, vous devez vous assurer de disposer de certains prérequis techniques. Tout d'abord, l'URL de base de l'API est https://sms.mtncongo.net/api/sms/

Ensuite, pour accéder à l'API, vous devez obtenir un token d'authentification disponible dans l'onglet info API de votre interface Profil. Ce token doit être inséré dans l'en-tête (header fields) de chaque requête que vous envoyez à l'API, avec l'en-tête Authorization: Token-xxxxxxxxxxxxxxxx où "xxxxxxxxxxxxxxxx" représente votre token personnel.
Le type MIME accepté par l'API est le format JSON, donc les données que vous envoyez à l'API doivent être structurées en JSON. Vous devez également définir l'en-tête Content-Type comme étant application/json.

Voici un exemple qui inclut les conditions préalables requises:

```python
POST https://sms.mtncongo.net/api/sms/

header {
    "Content-type": "application/json; charset=utf-8",
    "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxx"
} 

data {
    # Informations à inclure dans le message SMS
} 
```


## Envoie SMS et mails Non personnalisé

```python
POST https://sms.mtncongo.net/api/sms/

header {
    "Content-type": "application/json; charset=utf-8",
    "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxx"
} 

data {
    "msg": "Hello word 21",
    "msg_mail": "Hello word 20\n brel maxpro",
    "objet_mail": "test mail brel",
    "receivers": "242068463499,242068463499",
    "email": "brel.asseh@gmail.com",
    "date_envois": "2021-07-22T07:18:08.831717",
    "sender": "BES",
    "externalId": 10,
    "callback_url": "https://www.besnode.com/api/momo_cb"
}

```

## Envoie SMS et mails Personnalisé

```python
POST https://sms.mtncongo.net/api/sms/

header {
    "Content-type": "application/json; charset=utf-8",
    "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxx"
} 

data {
    "msg": "Hello :P1 :P2, word bulk.",
    "msg_mail": "Hello :P1 :P2 word 20\n brel maxpro",
    "sender": "BES",
    "objet_mail": "test mail brel",
    "isemail": "1",
    "date_envois": "2021-07-22T07:18:08.831717",
    "params": "ASSEH;Brel;info@besnode.com;242064504545\r\nMOTOKOUA;Hegel;support@besnode.com;242057360000",
    "externalId": 10,
    "callback_url": "https://www.besnode.com/api/get_status"
}
```


## Codes et vérification status réponses

```python
POST https://sms.mtncongo.net/api/sms/

header {
    "Content-type": "application/json; charset=utf-8",
    "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxx"
} 

data {
    "op": "status",
    "id": "26"
}
```

