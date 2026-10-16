# [Titlul proiectului]

Proiect individual la disciplina Metode avansate de programare, anul universitar 2026-2027.

## Autor

- **Nume:** Darva Victor-Marius
- **Grupa:** anul 3 grupa 1.2
- **Marca:** LH715243
- **Tema:** 3 - Catalog de note0

## Descriere

Aplicatia este un catalog de note dezvoltat pentru gestionarea studentilor si a notelor obtinute de acestia la diferite discipline. Aceasta permite adaugarea studentilor, inregistrarea notelor pe discipline si generarea automata de rapoarte cu mediile generale si statistici pe materii.

## Tehnologii

Python 3.13 cu Flask

## Rulare

```
docker build -t map-proiect .
docker run -d -p 8080:8080 map-proiect
```

Aplicatia asculta pe portul 8080. Verificati:

```
curl http://localhost:8080/health
curl http://localhost:8080/version
```

## Testare

```
pip install -r requirements.txt pytest pytest-cov
python -m pytest --cov=src
```

## Rutele implementate

| Ruta | Metoda | Descriere |
|---|---|---|
| `/health` | GET | Starea serviciului |
| `/version` | GET | Versiunea si commit-ul din care a fost construita imaginea |
| `/` | GET | Pagina de prezentare |
| `/reset` | POST | Goleste datele din memorie |
| [ruta temei] | [metoda] | [descriere] |

## Decizii de implementare

Stocarea datelor in memorie: Utilizarea structurilor de date native (liste si dictionare) pentru asigurarea unei viteze ridicate de executie si a simplitatii, respectand cerinta ca starea sa se pastreze exclusiv in memorie.

Rotunjirea mediilor: Implementarea unei logici dedicate de rotunjire la doua zecimale prin rotunjire la jumatate in sus, pentru garantarea preciziei cerute la calculul mediilor.

Gestionarea cazurilor speciale: Tratarea explicita a situatiei studentilor fara note, prin returnarea valorii null in loc de zero pentru medie, conform contractului strict al temei.