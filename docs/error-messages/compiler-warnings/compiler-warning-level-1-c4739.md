---
title: Ошибка компилятора предупреждение (уровень 1) C4739 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4739
dev_langs:
- C++
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c90acdbc8ab32522e8e7cfac079547caaf84398d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4739"></a>Предупреждение компилятора (уровень 1) C4739
ссылка на переменную var выходит за пределы ее области хранения  
  
 Переменной было назначено значение, но это значение больше, чем размер переменной. Запись в память будет выполнена за пределами расположения этой переменной в памяти, и возможна потеря данных.  
  
 Чтобы устранить это предупреждение, просто назначьте значение той переменной, размер которой может вместить это значение.  
  
 В следующем примере возникает ошибка C4739:  
  
```  
// C4739.cpp  
// compile with: /RTCs /Zi /W1 /c  
char *pc;  
int main() {  
   char c;  
   *(int *)&c = 1;   // C4739  
  
   // OK  
   *(char *)&c = 1;  
}  
```