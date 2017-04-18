---
title: "Предупреждение (уровень 1) C4722 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a88d734f0f17437efe3b4a60a3439135b7feec4e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4722"></a>Предупреждение компилятора (уровень 1) C4722
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
