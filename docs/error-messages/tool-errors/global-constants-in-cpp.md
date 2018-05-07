---
title: Глобальные константы в C++ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f1ee5fdf3d50f30e02bd48fe3664c10d26a8449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="global-constants-in-c"></a>Глобальные константы в C++
Глобальные константы в C++ имеют статическую связь. Это отличается от C. При попытке использования глобальных констант в C++ в нескольких файлах можно получить неразрешенная внешняя ошибка. Компилятор оптимизирует глобальные константы, не оставляя места для переменной.  
  
 Один из способов устранения этой ошибки является включение инициализации констант в файл заголовка и ввести этот заголовок в CPP-файлов при необходимости, как если бы он был прототип функции. Другой вариант — присвоить переменной неконстантное и использовать ссылку на константу при оценке его.  
  
 Следующий пример приводит к возникновению ошибки C2019:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 Затем:  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)