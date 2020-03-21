---
title: Ошибка компилятора C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3446
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 2e1e474b27fec6c1625136e526add0935e309746
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075020"
---
# <a name="compiler-error-c3446"></a>Ошибка компилятора C3446

>"*класс*": инициализатор членов по умолчанию не допускается для члена класса значений

В Visual Studio 2015 и более ранних версиях компилятор допускал (но игнорировал) инициализатор членов по умолчанию для члена класса значений. Инициализатор по умолчанию для класса значений всегда инициализирует члены нулевым значением. Конструктор по умолчанию не допускается. В Visual Studio 2017 инициализаторы членов по умолчанию вызывают ошибку компилятора, как показано в следующем примере:

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3446 в Visual Studio 2017 и более поздних версий:

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

Чтобы исправить эту ошибку, удалите инициализатор:

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```
