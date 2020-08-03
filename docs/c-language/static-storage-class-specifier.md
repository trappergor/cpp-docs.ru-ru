---
title: Спецификатор класса хранения static
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: e84e2745c6077f038f47295119936a1ad6431bdd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229497"
---
# <a name="static-storage-class-specifier"></a>Спецификатор класса хранения static

Переменная, объявленная на внутреннем уровне с помощью описателя класса хранения **`static`** , имеет глобальное время существования, но доступна только внутри блока, в котором она объявлена. Описатель **`static`** полезно использовать в константных строках, потому что при этом снимается нагрузка частой инициализации в часто вызываемых функциях.

## <a name="remarks"></a>Примечания

Если переменная с типом **`static`** не инициализирована явно, она инициализируется со значением 0 по умолчанию. Внутри функции **`static`** выделяет хранилище и служит определением. Внутренние статические переменные представляют закрытое постоянное хранилище, видимое только одной функции.

## <a name="see-also"></a>См. также

[Классы хранения в C](c-storage-classes.md)<br/>
[Storage classes (C++)](../cpp/storage-classes-cpp.md) (Классы хранения (C++))
