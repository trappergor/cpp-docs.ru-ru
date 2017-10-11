---
title: "Ошибка компилятора C2015 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4669eec9d8134db6e024257855012eb78dcef95e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2015"></a>Ошибка компилятора C2015
слишком много знаков в константе  
  
 Символьная константа содержит более двух знаков. Ограничение составляет один символ в стандартных и два символа для длинных символьных констант.  
  
 Escape-последовательность, например \t, преобразуется в один символ.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2015:  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## <a name="example"></a>Пример  
 C2015 также может возникнуть при использовании расширения Microsoft, символьные константы, преобразуются в целые числа.  Следующий пример приводит к возникновению ошибки C2015:  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```
