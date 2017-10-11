---
title: "Ошибка компилятора C2464 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7e2600608ae490363d9042ad72ad91bf7cfe32d2
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2464"></a>Ошибка компилятора C2464
«Идентификатор»: нельзя использовать «new» для выделения памяти для ссылки  
  
 Идентификатор ссылки был выделен с помощью `new` оператор. Ссылки не являются объектами памяти, поэтому `new` не может вернуть указатель на них. Используйте стандартные объявление переменной синтаксис для объявления ссылки.  
  
 Следующий пример приводит к возникновению ошибки C2464:  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```
