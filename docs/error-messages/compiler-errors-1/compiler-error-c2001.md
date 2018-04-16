---
title: Ошибка компилятора C2001 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 1c23e188db9e811122102259f5fa93733d29f00f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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