---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: a30840aa0556a7324ba24c0f2aaec57dea88d082
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367856"
---
# <a name="noreturn"></a>noreturn

**Microsoft Специфический**

Этот **__declspec** атрибут апогея говорит компилятору, что функция не возвращается. Как следствие, компилятор знает, что код, следующий за вызовом **функции __declspec (безвозврата),** недосягаем.

Если компилятор обнаруживает функцию с путем элемента управления, которая не возвращает значение, он создает предупреждение (C4715) или сообщение об ошибке (C2202). Если путь управления не может быть достигнут из-за функции, которая никогда не возвращается, вы можете использовать **__declspec (безвозврат)** для предотвращения этого предупреждения или ошибки.

> [!NOTE]
> Добавление **__declspec (безвозврат)** к функции, которая, как ожидается, вернется, может привести к неопределенному поведению.

## <a name="example"></a>Пример

В следующем примере положение **не** содержит оператора возврата.  Объявление `fatal` **как __declspec (безвозврат)** позволяет избежать ошибки или предупреждения.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
