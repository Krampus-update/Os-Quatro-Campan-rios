---
Moedas:
  Cealdica:
    Monótono: 0
    Jota: 0
    Talento: 0
    Março: 0
  Vintanesa:
    Centa: 0
    Centavo: 0
    Bit: 0
    QBit: 0
    Roda: 0
    Real: 0
  Republicanas:
    Moe: 0
    Ferro: 0
    Cobre: 0
    Prata: 0
    Republica: 0
Lore: ""
Caracteristica:
  Nome: <% tp.file.title %>
  Pronome: 
  Altura: 
  Peso: 
  Idade: 5005
  Nacionalidade: ""
  Cidade: ""
Notas: ""
fc-date:
  day: 1
  month: 1
  year: 
fc-category: Nascimentos
---
![[Personagens/Arthur Schmiedelegende/IMG-17092024-151137240.png|center]]
> [!recite]- Configurações 
> Nome: `INPUT[text(placeholder(Nome ✍)):Caracteristica.Nome]`
> Altura (em cm): `INPUT[number:Caracteristica.Altura]`
> Peso: `INPUT[number:Caracteristica.Peso]`
> Dinheiro: `INPUT[number:Moedas.Cealdica.Calço]`
> Nacionalidade: `INPUT[text(placeholder(ex: Brasileiro)):Caracteristica.Nacionalidade]`
> Cidade:`INPUT[text(placeholder(Sua cidade natal)):Caracteristica.Cidade]`
> > [!recite]- Nascimento
> > `VIEW[Dia: {fc-date.day}][text]` `INPUT[slider(minValue(1),maxValue(44),defaultValue(1)):fc-date.day]` 
> > `VIEW[Mês: {fc-date.month}][text]` `INPUT[slider(minValue(1),maxValue(8),defaultValue(1)):fc-date.month]` 
> > Ano: `INPUT[number(defaultValue(5005)):fc-date.year]` 
> > Idade: `VIEW[5005-{fc-date.year}][math:Caracteristica.Idade]`
---

| Características |                                                                                                 |
| :-------------: | :---------------------------------------------------------------------------------------------: |
|      Nome       |                                  `VIEW[{Caracteristica.Nome}]`                                  |
|      Idade      |                                 `VIEW[{Caracteristica.Idade}]`                                  |
|     Altura      |                             `VIEW[{Caracteristica.Altura} cm to m]`                             |
|      Peso       |                                `VIEW[{Caracteristica.Peso} kg]`                                 |
|  Nacionalidade  |                             `VIEW[{Caracteristica.Nacionalidade}]`                              |
|     Cidade      |                                 `VIEW[{Caracteristica.Cidade}]`                                 |
|     Pronome     | `INPUT[suggester(option(Ele/Dele), option(Ela/Dela), option(Elu/Delu)):Caracteristica.Pronome]` |

---
> [!recite]- Inventário
> ```meta-bind
> INPUT[list:Inventario]
> ```

---
> [!recite]- Bolsa
> | Cealdica |                                   Valor                                    |
| :------: | :------------------------------------------------------------------------: |
|  Calço   |                  `VIEW[round({Moedas.Cealdica.Calço},2)]`                  |
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
>
>| Republicanas |                                        Valor                                        |
| :----------: | :---------------------------------------------------------------------------------: |
|     Moe      |     `VIEW[round({Moedas.Cealdica.Calço}/1.25,2)][math:Moedas.Republicanas.Moe]`     |
|    Ferro     | `VIEW[round({Moedas.Republicanas.Moe}/2.5,2)][math:Moedas.Republicanas.Ferro]`  |
|    Cobre     |   `VIEW[round({Moedas.Republicanas.Ferro}/2,2)][math:Moedas.Republicanas.Cobre]`    |
|    Prata     |   `VIEW[round({Moedas.Republicanas.Cobre}/10,2)][math:Moedas.Republicanas.Prata]`   |
|  República   | `VIEW[round({Moedas.Republicanas.Prata}/12,2)][math:Moedas.Republicanas.Republica]` |
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
