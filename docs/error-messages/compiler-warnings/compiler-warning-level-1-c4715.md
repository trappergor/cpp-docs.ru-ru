---
title: Предупреждение компилятора (уровень 1) C4715 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4715
dev_langs:
- C++
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b3de829992bfa650280768a2fcd761feaeaece0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061374"
---
# <a name="compiler-warning-level-1-c4715"></a>Предупреждение компилятора (уровень 1) C4715

«функция»: не все пути возвращают значение

Указанную функцию, потенциально не может возвращать значение.

## <a name="example"></a>Пример

```
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

Чтобы устранить это предупреждение, измените код, в котором все пути задать возвращаемое значение функции:

```
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

Это возможно, что ваш код может содержать вызов функции, которая не возвращает ресурсы, как показано в следующем примере:

```
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

Этот код также создает предупреждение, поскольку компилятор не знает, `fatal` никогда не возвращает. Чтобы предотвратить этот код генерирует сообщение об ошибке, объявите `fatal` с помощью [__declspec(noreturn)](../../cpp/noreturn.md).