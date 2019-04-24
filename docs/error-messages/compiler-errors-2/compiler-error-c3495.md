---
title: Ошибка компилятора C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3e387fe77c521a4f25ba67205f1fbd552397e272
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035826"
---
# <a name="compiler-error-c3495"></a>Ошибка компилятора C3495

var : передаваемый параметр лямбда-выражения должен иметь длительность автоматического хранения

Вы не можете передавать переменную, которая не поддерживает автоматическую длительность хранения, например переменную, помеченную как `static` или `extern`.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Не передавайте переменную по `static` или `extern` в список передаваемых параметров лямбда-выражения.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3495, так как в списке передаваемых параметров лямбда-выражения присутствует переменная `static` `n` .

```
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)

