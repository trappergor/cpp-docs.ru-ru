---
title: Предупреждение (уровень 1) C4722 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 143a902a4d05ab73df96f3f8ab35f52dab244df4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282588"
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