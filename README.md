# Szybciutkie-Potegowanko

## Wprowadzenie

Szybkie potęgowanie to algorytm obliczania potęg w czasie logarytmicznym względem wykładnika, co znacząco przyspiesza operacje w porównaniu do naiwnych podejść liniowych. Poniżej przedstawione i omówione zostały dwie metody takiego potęgowania, iteracyjna i rekurencyjna.

## Omówienie dwóch metod

### Metoda Iteracyjna

```python
# Iteracyjna funkcja
def szybkie_iteracyjne(podstawa, eksponent):
    result = 1
    while eksponent > 0:
        if eksponent % 2 == 1:  # Jesli wykladnik jest nieparzysty
            result *= podstawa
        podstawa *= podstawa
        eksponent //= 2
    return result
```

### Metoda Rekurencyjna

```python
# Rekurencyjna funkcja
def szybkie_rekurencyjne(podstawa, eksponent):
    if eksponent == 0:
        return 1
    if eksponent % 2 == 0:
        polowa_potegi = szybkie_rekurencyjne(podstawa, eksponent // 2)
        return polowa_potegi * polowa_potegi
    else:
        return podstawa * szybkie_rekurencyjne(podstawa, eksponent - 1)
```

## Złożoność Obliczeniowa

1. **Złożoność Czasowa**:
   - Zarówno w wersji iteracyjnej, jak i rekurencyjnej algorytm wykonuje operacje proporcjonalne do liczby bitów w wykładniku. Wartość ta wynosi log<sub>2</sub>(exponent). Dlatego złożoność czasowa wynosi **O(log n)**, gdzie *n* to wykładnik.

2. **Złożoność Pamięciowa**:
   - Wersja iteracyjna ma złożoność pamięciową **O(1)**, ponieważ używa stałej ilości zmiennych.
   - W wersji rekurencyjnej dodatkowo zachowywany jest stos wywołań rekurencyjnych, co skutkuje złożonością pamięciową **O(log n)**.

## Przykłady Użycia

```python
# Przykład użycia wersji iteracyjnej
print(fast_power_iterative(2, 10))  # Output: 1024

# Przykład użycia wersji rekurencyjnej
print(fast_power_recursive(2, 10))  # Output: 1024
```

## Podsumowanie

Szybkie potęgowanie jest wydajnym algorytmem umożliwiającym obliczanie potęg w czasie logarytmicznym. Wersja iteracyjna jest bardziej efektywna pamięciowo, natomiast rekurencyjna jest bardziej przejrzysta i prostsza do implementacji w wielu przypadkach.

**Zachęcam do eksperymentowania z obiema wersjami i analizy ich wydajności w różnych scenariuszach!**

