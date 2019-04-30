---
title: Предупреждение компилятора (уровень 1) C4722
ms.date: 11/04/2016
f1_keywords:
- C4722
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
ms.openlocfilehash: 320061c2daf2be042afe45828af637638399beaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327292"
---
# <a name="compiler-warning-level-1-c4722"></a>Предупреждение компилятора (уровень 1) C4722

"функция": деструктор не возвращает ресурсы, возможна утечка памяти

Поток управления завершается в деструкторе. Поток или вся программа завершится, и выделенные ресурсы могут не освободиться.  Кроме того, если деструктор будет вызван для очистки стека во время обработки исключения, поведение исполняемого файла может быть неопределенным.

Для решения проблемы удалите вызов функции, являющийся причиной невозвращения деструктора.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4722:

```
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