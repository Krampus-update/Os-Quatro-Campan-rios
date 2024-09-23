---
descricao: ""
---
![[Assets/d95c80be0d8a1a7d059417053e1bf21a_MD5.webp#banner]]

```meta-bind
INPUT[editor:descricao]
```
**
> [!recite]+ Jogadores
> ```dataview
> TABLE WITHOUT ID caracteristica.Nome as "Nome", caracteristica.Idade as "Idade", Moedas.Cealdica.Calço as "Dinheiro"
> FROM -#no and "Personagens"
>```
---
> [!recite]- Professores
> ```dataview
> TABLE WITHOUT ID file.name AS "Nome", materia AS "Matéria"
> FROM  "NPCs"
> WHERE materia
> ``` 
---
> [!recite]- NPCs
> ```dataview
> TABLE WITHOUT ID file.name AS "Nome", funcao AS "Função"
> FROM  "NPCs"
> WHERE !materia
> ``` 
---
> [!recite]+ Calendário 
> ```calendarium
> calendar: Temerant
>```
