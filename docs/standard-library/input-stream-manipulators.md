---
title: Манипуляторы входных потоков
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: 17f18aa127b84538229b3cf4e4246dfefb6c1f98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517967"
---
# <a name="input-stream-manipulators"></a>Манипуляторы входных потоков

Многие манипуляторы, такие как [setprecision](../standard-library/iomanip-functions.md#setprecision), определенных для `ios` класса и таким образом применяются к входным потокам. Однако некоторые манипуляторы фактически влияют на объекты потока ввода. Наиболее важными из них являются манипуляторы основания системы счисления `dec`, `oct` и `hex`, которые определяют базу преобразования, используемую с числами из входного потока.

При извлечении манипулятор `hex` позволяет обрабатывать различные форматы входных данных. Например, c C, 0xc, 0xC, 0Xc и 0XC интерпретируются как десятичное целое число 12. Любой символ, отличный от цифр от 0 до 9, букв от A до F, букв от a до f, x и X, завершает числовое преобразование. Таким образом, последовательность `"124n5"` преобразуется в число 124 с заданными битом [basic_ios::fail](../standard-library/basic-ios-class.md#fail).

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
