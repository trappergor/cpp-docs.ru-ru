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
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7f29cb8fb61dfc9f50cc5677e0d4f18f83627cdb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="function-inlining-problems"></a>Проблемы при встраивании функций
Если вы используете встраивания функции, необходимо выполнить следующее:  
  
-   Имеет встроенные функции, реализованные в файле заголовка, которые включены.  
  
-   У встраивания в файле заголовка.  
  
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
  
 Если вы используете `#pragma inline_depth` компилятора директив, убедитесь, что у вас есть значение 2 или более поздней версии. Значение&0; отключает встраивания. Также убедитесь, что вы используете **/Ob1** или **/Ob2** параметры компилятора.  
  
 Смешивание в тексте, а не встроенных параметров компилятора для различных модулей могут возникнуть проблемы. Если библиотека C++ создана с функциональная возможность встраивания включена ([/Ob1](../../build/reference/ob-inline-function-expansion.md) или [/Ob2](../../build/reference/ob-inline-function-expansion.md)), но встраивание в соответствующем файле заголовка с описанием функций отключена (нет параметров), возникает ошибка LNK2001. Функции не встраиваются в код из файла заголовка, но поскольку они не находятся в файле библиотеки нет адреса для разрешения ссылки.  
  
 Аналогичным образом проект, использующий встраивания функции определяющий функции еще в CPP-файле, а не в заголовке файла также получат ошибку LNK2019. Файл заголовка включается необходимости везде, но функции являются только встроенных при CPP-файл передает компилятора; Таким образом компоновщик будет видеть эти функции как неразрешенных внешних элементов при использовании в других модулях.  
  
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
