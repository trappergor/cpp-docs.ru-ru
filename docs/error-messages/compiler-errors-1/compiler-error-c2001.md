---
title: "Ошибка компилятора C2001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aedba438451089aa2d71e06da7ce189ab97d4190
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2001"></a>Ошибка компилятора C2001
символ новой строки в константе  
  
 Строковая константа не может быть продолжено во второй строке, пока вы не выполните следующее:  
  
-   Конец первой строки обратную косую черту.  
  
-   Закройте строки в первой строке с двойной кавычкой и откройте строку на следующую строку с другой двойных кавычек.  
  
 Завершить первую строку с \n недостаточно.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2001:  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## <a name="example"></a>Пример  
 Пробелы в начале следующей строки после символ продолжения строки включаются в строковую константу. Ни один из приведенных выше примеров внедрения символа новой строки в строковую константу. Можно внедрять символ перевода строки, как показано ниже:  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```
