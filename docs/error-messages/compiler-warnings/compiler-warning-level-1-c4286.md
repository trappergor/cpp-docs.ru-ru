---
title: Предупреждение компилятора (уровень 1) C4286 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4286
dev_langs:
- C++
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1a796ee1956de0795f677afec90dd2a65bb3d1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099529"
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