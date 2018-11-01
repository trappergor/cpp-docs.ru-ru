---
title: Ошибка компилятора C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 7cba9e0271d16420c5cfe4adbed2c7121d139d8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523929"
---
# <a name="compiler-error-c3539"></a>Ошибка компилятора C3539

«Тип»: аргумент шаблона не может быть тип, содержащий «auto»

Указанный тип аргумента шаблона не может содержать `auto` ключевое слово.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не указывайте аргумент шаблона с `auto` ключевое слово.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3539.

```
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)