---
title: "Проблемы при встраивании функций | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97ffa56fc748eea8f65f5fe79c7a9defa7238f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="function-inlining-problems"></a>Проблемы при встраивании функций
Если вы используете встраивания функции, необходимо выполнить следующее:  
  
-   Имеет встроенные функции, реализованные в файле заголовка, которые включены.  
  
-   Иметь встраивания в файле заголовка.  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 Затем:  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 Если вы используете `#pragma inline_depth` компилятора директив, убедитесь, что у вас есть значение 2 или более поздней. Значение 0 отключает встраивания. Также убедитесь, что вы используете **/Ob1** или **/Ob2** параметры компилятора.  
  
 Смешение параметров компиляции встроенной и не являющиеся встроенными в различных модулях могут возникнуть проблемы. Если библиотека C++ создается с функциональная возможность встраивания включена ([/Ob1](../../build/reference/ob-inline-function-expansion.md) или [/Ob2](../../build/reference/ob-inline-function-expansion.md)), но встраивания в соответствующем файле заголовка с описанием функций отключена (без параметров), возникнет ошибка LNK2001. Функции не встраиваются в код из файла заголовка, но поскольку они не находятся в файле библиотеки нет адреса для разрешения ссылки.  
  
 Аналогичным образом проект, использующий встраивания функции определяет функции еще в CPP-файле, а не в заголовке файла также получат ошибку LNK2019. Файл заголовка включается необходимости везде, но функции являются только встроенных когда CPP-файл проходит через компилятора. Таким образом компоновщик будет видеть эти функции виде неразрешенных внешних ссылок при использовании в других модулях.  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 И потом  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 И потом  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)