---
title: Предупреждение компилятора (уровень 1) C4722
ms.date: 11/04/2016
f1_keywords:
- C4722
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
ms.openlocfilehash: 85921d67b764a28f9251f0c8b6e3fc807edd0f5b
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052455"
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