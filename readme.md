## Data folder

-   Ca sa nu fie probleme cand rulezi codul din notebook-urile jupyter, pune setul de date (csv ul) in data/raw 

## Setup la env

### La virtual env ruleaza (macos):

```console
source venv/bin/activate
```

### Pentru a instala pachetele pe care le folosim:

```console
pip install -r requirements.txt
```

OBS:

-   Comanda ruleaza-o din root ca sa nu fie probleme in caz ca nu ti gaseste path ul

-   Urmeaza ordinea pe care o dau aici, adica mai intai activezi env-ul si apoi install la requirements

### Pentru a salva un pachet in requirements in caz ca vrei sa folosesti ceva anume

```console
pip install pachet
```

```console
pip freeze > requirements.txt
```