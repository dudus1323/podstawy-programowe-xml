# Podstawy programowe w formie plików XML
W tym repozytorium znajdują się pliki XML z podstawami programowymi dla szkół ponadpodstawowych obowiązujących od 2025 roku.
## Struktura pliku XML
Podstawa programowa znajduje się węźle: `<podstawaProgramowa>`, która posiada następujące atrybuty:
- `szkola` - przyjmuje wartości (`"podstawowa"`, `"ponadpodstawowa"`);
- `przedmiot` - oznacza przedmiot szkolny, którego dotyczy podstawa;
- `zakres` - przyjmuje wartości (`"podstawowy"`, `"rozszerzony"`);
- `obowiazujeOd` - oznacza datę wejścia w życie w formacie `YYYY-MM-DD`.

Dalej struktura dokumentu przebiega jak niżej:
```
<dzial>
    <nazwa></nazwa>
    <wymaganie></wymaganie>
    <rozdzial>
          <nazwa></nazwa>
          <wymaganie></wymaganie>
          <podRozdzial>
              <nazwa></nazwa>
              <wymaganie></wymaganie>
          </podRozdzial>
    </rozdzial> 
</dzial>
```
Struktura dla węzła `<dzial>`:
| Pole/węzeł| Występowanie | Warunek występowania |
| ----------- | ----------- | ----------- |
| `<nazwa>` | Pojedyncze | Zawsze |
| `<wymaganie>` | Wielokrotne | Zawsze, gdy brak węzła `<rozdzial>` w węźle `<dzial>` |
| `<rozdzial>` | Wielokrotne |  Zawsze, gdy brak pola `<wymaganie>` w rodzicu |

Struktura dla węzła `<rozdzial>`, gdy istnieje:
| Pole/węzeł| Występowanie | Warunek występowania |
| ----------- | ----------- | ----------- |
| `<nazwa>` | Pojedyncze | Zawsze |
| `<wymaganie>` | Wielokrotne | Zawsze, gdy brak węzła `<podRozdzial>` w węźle `<rozdzial>` |
| `<podRozdzial>` | Wielokrotne | Zawsze, gdy brak pola `<wymaganie>` w rodzicu |

Struktura dla węzła `<podRozdzial>`, gdy istnieje:
| Pole/węzeł| Występowanie | Warunek występowania |
| ----------- | ----------- | ----------- |
| `<nazwa>` | Pojedyncze | Zawsze |
| `<wymaganie>` | Wielokrotne | Zawsze, gdy brak pola `<wymaganie>` w rodzicu  |




