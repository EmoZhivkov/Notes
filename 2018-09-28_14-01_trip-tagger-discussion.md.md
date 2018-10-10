---
tags:
  - trip-tagger
---

1. need to see the query pattern
2. really write heavy, not so much read
3. need to structure the trip so it is easier to search
    - trqbwa da widim kak da gi pazim v elastic search
    - log-ingestion pipeline - nqma da imame mn kakwo da konigurirame
    - mojem da gi pazim po tagowe, da ima razlichni indexi za wseki tag
    - da probvame nqkakuv lesen nachin otnachalo, samo da тагва по един таг, така че да видим
    как ще се държи

4. CRO and RRO
    - bill - status success
    - bill - status -4$
    - cro and rro trigger

5. handler - configure to listen on cro, in order

6. simulate in elastic search 10 jsons that have the have the same client and uuid but different tags,
so we could see if elasticsearch can adequatly show us the information

7. Трябва да симулирам еластик с примерно 4/5 шарда

8. Да генерирам около милион документа, за да тестваме от перформънц
гледна точка
