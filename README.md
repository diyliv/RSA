# RSA 
`RSA` - криптографический алгоритм ассиметричного шифрования  
В данном алгоритме используются два ключа. Приватный и публичный(private&public)  
В основе данного алгоритма лежат простые числа.  
Простые числа - это числа, которые делятся на себя и на единицу.

## Пример простых чисел
`2` - является простым числом(делится на 2 и на 1)  
`3` - является простым числом(делится на 3 и на 1)  
`4` - не является простым числом(делится на 1, на 2, на 4)
## Генерация публичного ключа
Для генерации публичного ключа нам нужны два простых числа. Например 2 и 5 (2 делится на себя и на единицу. 5 делится на себя и на единицу)  
Публичный ключ состоит из модуля(mod) и открытой экспоненты(e)  
`2` - будет являтся нашим первым множителем - p  
`5` - будет являтся нашим вторым множителем - q  
Перемножим  
2(p) * 5(q) = 10(mod)  
`Ф-ция Эйлера`  
ф = (p - 1) * (q - 1) = (2 - 1) * (5 - 1) = 4  
`Открытая экспонента и ее свойства`  
* Простое число
* Должна быть меньше `ф` (2, 3 в нашем случае)
* Взаимно простое с `ф` (т.е не иметь общих делителей с числом 4. 2 не подходит, остается 3)  
{e, mod} - открытый ключ  
{e, mod} = {3, 10} ф = 4

## Генерация приватного ключа
{d, mod} где d - число обратное e по модулю ф  
(d * e) % ф = 1  
(d * 3) % 4 = 1  
Пусть d = 7, тогда верно ли выражение (7 * 3) % 4 = 1?. 21 % 4 = 1. Да, верно. Тогда d = 7  
Вот чему равен наш приватный ключ: {7, 10}  

## Шифрование 
{e, mod} = {3, 10}
При шифровании наше число должно быть меньше модуля.   
x < mod  
x < 10   
x = 8  
Мы должны возвести 8 в e.  
8 ^ 3 = 512  
И разделим на наш модуль  
512 % 10 = 2(мы должны передать это число нашему собеседнику, чтобы он мог его расшифровать)

## Дешифрование
{d, mod} = {7, 10}
Для того, чтобы расшифровать сообщение должны:  
2 возвести в 7 = 128  
128 % 10 = 8(наше первоначальное сообщение)


