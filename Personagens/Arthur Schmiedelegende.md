---
Lore: |-
  Arthur era um jovem nascido na movimentada cidade de Lature, localizada ao lado de um vulcão ativo no Império Arturiano. A cidade era conhecida por seus ricos depósitos de minerais que eram minerados e usados para criar poderosas armas para a guerra contínua contra demônios. Lature também era conhecida como o berço dos ferreiros mais habilidosos do império.
  Apesar de crescer em uma cidade cheia de artesãos talentosos e guerreiros, Arthur sentia que não se encaixava completamente. Ele não era o melhor ferreiro nem o mais forte mineiro, e frequentemente se perguntava qual era seu verdadeiro propósito na vida.
  Em um dia fatídico, um homem misterioso da Universidade, uma instituição de prestígio conhecida por seus estudos avançados em ciência e magia, visitou Lature. Intrigado pela natureza inquisitiva de Arthur e sua sede de conhecimento, o homem o apresentou ao conceito de "simpatia".
  A simpatia era uma forma rara e poderosa de magia que permitia às pessoas estabelecerem conexões profundas com o mundo ao seu redor, semelhante ao emaranhamento quântico. O homem da Universidade viu um grande potencial em Arthur e o convidou a estudar na instituição, onde ele poderia dominar e aprimorar essa habilidade única.
  Determinado a descobrir sua verdadeira vocação, Arthur aceitou a oferta do homem e embarcou em uma jornada rumo à Universidade. No caminho, o homem ensinou a Arthur os princípios básicos.
  Apesar de enfrentar muitos desafios e dúvidas ao longo do caminho, o talento natural e a determinação inabalável de Arthur impressionaram os professores da Universidade, Fazendo ele ser aprovado na Universidade.
Caracteristica:
  Nome: Arthur Schmiedelegende
  Pronomes: Ele/Dele
  Altura: 192
  Peso: 110
  Idade: 19
  Pronome: Ele/Dele
  Nacionalidade: Arturiano
  Cidade: Lature
Notas: |
  Trabalho na [[Lugares/Taverninha Bom Encanto|Taverninha Bom Encanto]] se eu trabalhar final de semana eu ganho extra.
   ```dataview
   TABLE WITHOUT ID file.name AS "Nome", materia AS "Matéria"
   FROM  "NPCs"
   WHERE materia
  ```
fc-date:
  year: 4986
  day: 12
  month: 6
fc-category: Nascimentos
Inventario:
  - Espada (Encantada)
  - 4 Acido de Lagarto de Fogo
Moedas:
  Cealdica:
    Monótono: 193.7
    Jota: 19.37
    Talento: 1.94
    Março: 0.19
    Calço: 1937
  Vintanesa:
    Centa: 322.83
    Centavo: 161.42
    Bit: 64.57
    QBit: 29
    Roda: 7
    Real: 2.9
  Republicana:
    Moe: 1549.6
    Prata: 30.99
    Republica: 2.58
    Ferro: 619.84
    Cobre: 309.92
  Republicanas:
    Ferro: 619.84
    Cobre: 309.92
    Republica: 2.58
    Prata: 30.99
---
> [!infobox]+
> ![[Assets/IMG-17092024-151137240.png]]
> #### Configurações 
> Altura (em cm): `INPUT[number:Caracteristica.Altura]`
> Peso: `INPUT[number:Caracteristica.Peso]`
> Nacionalidade: `INPUT[text(placeholder(ex: Brasileiro)):Caracteristica.Nacionalidade]`
> Cidade:`INPUT[text(placeholder(Sua cidade natal)):Caracteristica.Cidade]`
> #### Nascimento
> `VIEW[Dia: {fc-date.day}][text]` `INPUT[slider(minValue(1),maxValue(44),defaultValue(1)):fc-date.day]` 
> `VIEW[Mês: {fc-date.month}][text]` `INPUT[slider(minValue(1),maxValue(8),defaultValue(1)):fc-date.month]` 
> Ano: `INPUT[number(defaultValue(5005)):fc-date.year]` 
> Idade: `VIEW[5005-{fc-date.year}][math:Caracteristica.Idade]`
---


| Características |                                                                                                 |
| :-------------- | :---------------------------------------------------------------------------------------------- |
| Nome            | `= this.file.name`                                                                               |
| Idade           | `VIEW[{Caracteristica.Idade}]`                                                                  |
| Altura          | `VIEW[{Caracteristica.Altura} cm to m]`                                                         |
| Peso            | `VIEW[{Caracteristica.Peso} kg]`                                                                |
| Nacionalidade   | `VIEW[{Caracteristica.Nacionalidade}]`                                                          |
| Cidade          | `VIEW[{Caracteristica.Cidade}]`                                                                 |
| Pronome         | `INPUT[suggester(option(Ele/Dele), option(Ela/Dela), option(Elu/Delu)):Caracteristica.Pronome]` |

---
> [!recite]- Inventário
> ```meta-bind
> INPUT[list:Inventario]
> ```
---
> [!recite]- Bolsa
> | Cealdica |                                   Valor                                    |
| :------: | :------------------------------------------------------------------------: |
|  Calço   |                  `INPUT[number:Moedas.Cealdica.Calço]`                  |
| Monótono | `VIEW[round({Moedas.Cealdica.Calço}/10,2)][math:Moedas.Cealdica.Monótono]` |
|   Jota   | `VIEW[round({Moedas.Cealdica.Monótono}/10,2)][math:Moedas.Cealdica.Jota]`  |
| Talento  |  `VIEW[round({Moedas.Cealdica.Jota}/10,2)][math:Moedas.Cealdica.Talento]`  |
|  Março   | `VIEW[round({Moedas.Cealdica.Talento}/10,2)][math:Moedas.Cealdica.Março]`  |
> 
> ---
>
>| Vintanesa |                                   Valor                                    |
|:---------:|:--------------------------------------------------------------------------:|
|   Centa   |  `VIEW[round({Moedas.Cealdica.Calço}/6,2)][math:Moedas.Vintanesa.Centa]`   |
|  Centavo  | `VIEW[round({Moedas.Vintanesa.Centa}/2,2)][math:Moedas.Vintanesa.Centavo]` |
|    Bit    | `VIEW[round({Moedas.Vintanesa.Centavo}/2.5,2)][math:Moedas.Vintanesa.Bit]` |
|   QBit    |   `VIEW[round({Moedas.Vintanesa.Bit}/2.2)][math:Moedas.Vintanesa.QBit]`    |
|   Roda    |   `VIEW[round({Moedas.Vintanesa.QBit}/4.2)][math:Moedas.Vintanesa.Roda]`   |
|   Real    |  `VIEW[round({Moedas.Vintanesa.QBit}/10,2)][math:Moedas.Vintanesa.Real]`   |
> 
> ---
>| Republicanas |                                        Valor                                        |
| :----------: | :---------------------------------------------------------------------------------: |
|     Moe      |     `VIEW[round({Moedas.Cealdica.Calço}/1.25,2)][math:Moedas.Republicana.Moe]`     |
|    Ferro     | `VIEW[round({Moedas.Republicana.Moe}/2.5,2)][math:Moedas.Republicana.Ferro]`  |
|    Cobre     |   `VIEW[round({Moedas.Republicana.Ferro}/2,2)][math:Moedas.Republicana.Cobre]`    |
|    Prata     |   `VIEW[round({Moedas.Republicana.Cobre}/10,2)][math:Moedas.Republicana.Prata]`   |
|  República   | `VIEW[round({Moedas.Republicana.Prata}/12,2)][math:Moedas.Republicana.Republica]` |
>
---
> [!recite]- Notas
>```meta-bind
> INPUT[editor():Notas]
> ```
---
> [!recite]- Historia
> ```meta-bind
> INPUT[editor():Lore]
> ```