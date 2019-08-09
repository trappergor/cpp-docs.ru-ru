---
title: Перегрузка оператора &gt;&gt; для собственных классов
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 672dfb7ec40b2f18cbde0adc92522d3194a5e738
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450127"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Перегрузка оператора &gt;&gt; для собственных классов

Потоки ввода используют оператор извлечения (`>>`) для стандартных типов. Можно написать аналогичные операторы извлечения для собственных типов; успех зависит от правильности использования пустого пространства.

Ниже приведен пример оператора извлечения для класса `Date`, представленного выше.

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)
