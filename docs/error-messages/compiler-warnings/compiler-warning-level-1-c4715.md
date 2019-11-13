---
title: Предупреждение компилятора (уровень 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 268a26f5de1bb7f757a8e7cba6d3f5e6ddff882e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052477"
---
# <a name="compiler-warning-level-1-c4715"></a>Предупреждение компилятора (уровень 1) C4715

"функция": не все пути управления возвращают значение

Указанная функция потенциально может не возвращать значение.

## <a name="example"></a>Пример

```cpp
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

Чтобы предотвратить это предупреждение, измените код так, чтобы все пути применялись к возвращаемому значению функции:

```cpp
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

Возможно, ваш код содержит вызов функции, которая никогда не возвращает значение, как показано в следующем примере:

```cpp
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

Этот код также создает предупреждение, так как компилятор не знает, что `fatal` никогда не возвращает. Чтобы этот код не создавал сообщение об ошибке, объявите `fatal` с помощью [__declspec (noreturn)](../../cpp/noreturn.md).