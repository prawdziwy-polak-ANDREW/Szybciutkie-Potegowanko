# Szybciutkie-Potegowanko

## Wprowadzenie

Szybkie potęgowanie to algorytm obliczania potęg w czasie logarytmicznym względem wykładnika, co znacząco przyspiesza operacje w porównaniu do naiwnych podejść liniowych. W tym dokumencie przedstawione zostały implementacje algorytmu szybkiego potęgowania w wersji iteracyjnej i rekurencyjnej, wraz z omówieniem złożoności obliczeniowej.

## Implementacje

### Wersja Iteracyjna

```python
# Funkcja iteracyjna do szybkiego potęgowania
def fast_power_iterative(base, exponent):
    result = 1
    while exponent > 0:
        if exponent % 2 == 1:  # Jeśli wykładnik jest nieparzysty
            result *= base
        base *= base
        exponent //= 2
    return result
```

### Wersja Rekurencyjna

```python
# Funkcja rekurencyjna do szybkiego potęgowania
def fast_power_recursive(base, exponent):
    if exponent == 0:
        return 1
    if exponent % 2 == 0:
        half_power = fast_power_recursive(base, exponent // 2)
        return half_power * half_power
    else:
        return base * fast_power_recursive(base, exponent - 1)
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

