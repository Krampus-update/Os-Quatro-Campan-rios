---
descricao: ""
---
![[Assets/d95c80be0d8a1a7d059417053e1bf21a_MD5.webp#banner]]

```meta-bind
INPUT[editor:descricao]
```

> [!recite]+ Jogadores
> ```dataview
> TABLE WITHOUT ID file.link AS "Nome", caracteristica.Idade AS "Idade", Moedas.Cealdica.Calço AS "Dinheiro"
> FROM -#no and "Personagens"
>```
---
> [!recite]- Professores
> ```dataview
> TABLE WITHOUT ID file.link AS "Nome", materia AS "Matéria"
> FROM  "NPCs"
> WHERE materia
> ``` 
---
> [!recite]- NPCs
> ```dataview
> TABLE WITHOUT ID file.link AS "Nome", funcao AS "Função"
> FROM  "NPCs"
> WHERE !materia
> ``` 
---
> [!recite]+ Calendário 
> ```calendarium
> calendar: Temerant
>```
