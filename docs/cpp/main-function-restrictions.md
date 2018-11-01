---
title: Ограничения функции main
ms.date: 11/04/2016
f1_keywords:
- Main
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
ms.openlocfilehash: 9ccea987b05c7854e78ba1621fd6c0a065d73d5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555765"
---
# <a name="main-function-restrictions"></a>Ограничения функции main

Несколько ограничений **основной** функцию, которая не применяются для любых других функций C++. **Основной** функции:

- Не может быть перегружен (см. в разделе [перегрузка функций](function-overloading.md)).

- Не могут объявляться как **встроенного**.

- Не могут объявляться как **статических**.

- Нельзя получить ее адрес.

- Вызвать невозможно.

## <a name="see-also"></a>См. также

[Функция main: запуск программы](../cpp/main-program-startup.md)