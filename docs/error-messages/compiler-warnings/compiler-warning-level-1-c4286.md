---
title: Предупреждение компилятора (уровень 1) C4286
ms.date: 11/04/2016
f1_keywords:
- C4286
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
ms.openlocfilehash: be02d330678eaab7f538ed092641f957bdcb01b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455215"
---
# <a name="compiler-warning-level-1-c4286"></a>Предупреждение компилятора (уровень 1) C4286

«тип1»: перехвачено базовым классом («тип2») в строке с номером

Указанный тип исключения обрабатывается предыдущим обработчиком. Тип второго перехвата является производным от типа первого. Исключения для базового класса перехватывать исключения для производного класса.

## <a name="example"></a>Пример

```
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```