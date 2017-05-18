---
title: "Предупреждение (уровень 1) C4747 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: 10
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
ms.openlocfilehash: 7ecbfe8e2ace06cb6e667d77d315f544ce0b451c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4747"></a>Предупреждение компилятора (уровень 1) C4747
Вызов управляемого «точка_входа»: управляемый код может не выполняться во время блокировки загрузчика, точки входа DLL и поступившим из них вызовам  
  
 Компилятор обнаружил (возможно) точку входа DLL, скомпилированные в MSIL.  Из-за возможных проблем с загрузкой библиотеки DLL, точка входа которой была скомпилирована для MSIL рекомендуется компилировать функцию точки входа DLL в MSIL.  
  
 Дополнительные сведения см. в разделе [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md) и [Ошибка средств компоновщика LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не компилируйте модуль с **/CLR**.  
  
2.  Пометьте функцию точки входа с `#pragma unmanaged`.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4747.  
  
```  
// C4747.cpp  
// compile with: /clr /c /W1  
// C4747 expected  
#include <windows.h>  
  
// Uncomment the following line to resolve.  
// #pragma unmanaged  
  
BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {  
   return TRUE;  
};  
```
