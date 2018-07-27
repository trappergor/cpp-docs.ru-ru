---
title: Предупреждение (уровень 1) C4747 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 203943f3741d07e278652a7032a6dcdcb305a384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285828"
---
# <a name="compiler-warning-level-1-c4747"></a>Предупреждение компилятора (уровень 1) C4747
Вызов управляемого «точка входа»: управляемый код может не выполняться во время блокировки загрузчика, включая точки входа DLL и поступившим из них вызовам  
  
 Компилятор обнаружил (вероятного) точки входа библиотеки DLL, скомпилированные в MSIL.  Из-за потенциальных проблем с загрузкой был скомпилирован в код MSIL, точка входа библиотеки DLL рекомендуется компилировать функцию точки входа DLL в MSIL-код.  
  
 Дополнительные сведения см. в разделе [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md) и [Ошибка средств компоновщика LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не компилировать модуль с **/CLR**.  
  
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