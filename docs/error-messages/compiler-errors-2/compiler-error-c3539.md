---
title: Ошибка компилятора C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: be1051859ebbcbdc22a9b71f8c5adba2e75c4e92
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025184"
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