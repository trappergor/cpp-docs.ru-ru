---
title: "Предупреждение (уровень 1) C4744 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6fa95f8477f889aa8664d2b6d99c753cb9848d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4744"></a>Предупреждение компилятора (уровень 1) C4744
«переменная» имеет различные типы в «файл1» и «файл2»: «тип1» и «тип2»  
  
 Внешняя переменная определена в двух файлах или ссылаться на имеет различные типы в этих файлах.  Чтобы решить, сделать определения типа одинаковыми или изменить имя переменной, в один из файлов.  
  
 C4744 вызывается, только в том случае, если файлы были скомпилированы с параметром/GL.  Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  C4744 обычно возникает в файлах C (C++), так как в C++ имя переменной сведения о типе.  При компиляции образца (см. ниже) как C++, возникнет ошибка компоновщика LNK2019.  
  
## <a name="example"></a>Пример  
 В этом примере содержится первое определение.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4744.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```