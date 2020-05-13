---
title: Предупреждение компилятора (уровень 1) C4722
ms.date: 11/04/2016
f1_keywords:
- C4722
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
ms.openlocfilehash: 3fee3296eba4476680f4948b4a1f7fdee03e8840
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175211"
---
# <a name="compiler-warning-level-1-c4722"></a>Предупреждение компилятора (уровень 1) C4722

"функция": деструктор не возвращает ресурсы, возможна утечка памяти

Поток управления завершается в деструкторе. Поток или вся программа завершится, и выделенные ресурсы могут не освободиться.  Кроме того, если деструктор будет вызван для очистки стека во время обработки исключения, поведение исполняемого файла может быть неопределенным.

Для решения проблемы удалите вызов функции, являющийся причиной невозвращения деструктора.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4722:

```cpp
// C4722.cpp
// compile with: /O1 /W1 /c
#include <stdlib.h>
class C {
public:
   C();
   ~C() { exit(1); };   // C4722
};

extern void func (C*);

void Test(){
   C x;
   func(&x);
   // control will not leave Test because destructor will exit
}
```
