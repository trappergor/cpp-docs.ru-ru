---
title: Предупреждение (уровень 4) C4702 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29c2d6b0328fd8dd4cd6f9a226253036b62d03ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4702"></a>Предупреждение компилятора (уровень 4) C4702
недостижимый код  
  
 Это предупреждение отображается в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: недостижимый код. Когда компилятор (внутреннюю) обнаруживает недостижимый код, он создает C4702, предупреждение уровня 4.  
  
 Для кода, который допустим в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET удалите недостижимый код или убедиться, что все исходный код доступен для определенного потока выполнения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4702.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>Пример  
 При компиляции с параметром **/GX**, **параметр/EHc**, **/EHsc**, или **/EHac** и используя внешние функции C, код может стать недоступным из-за extern C функции считаются недоступными, поэтому блок catch недостижим.  Если вы считаете, что это предупреждение не является допустимым, так как функция, можно вызывать, компиляция с **/EHa** или **/EHs**, в зависимости от исключения.  
  
 Дополнительные сведения см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению ошибки C4702.  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```