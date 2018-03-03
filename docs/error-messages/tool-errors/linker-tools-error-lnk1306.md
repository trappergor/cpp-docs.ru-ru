---
title: "Ошибка средств компоновщика LNK1306 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32b6589fa5e4d7dc02ccb9a6c3157c109725b895
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1306"></a>Ошибка средств компоновщика LNK1306  
  
> Функция точки входа библиотеки DLL не может управляться; откомпилируйте в машинный код  
  
`DllMain`Невозможно скомпилировать в MSIL-код; его необходимо скомпилировать в машинный код.  
  
Чтобы устранить эту проблему  
  
-   Скомпилируйте файл, содержащий точку входа без **/CLR**.  
  
-   Поместите точку входа `#pragma unmanaged` раздела.  
  
Дополнительные сведения:  
  
-   [/ CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed, unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [Библиотеки DLL и поведение библиотеки времени выполнения Visual C++](../../build/run-time-library-behavior.md)  
  
## <a name="example"></a>Пример  
  
Следующий пример приводит к возникновению ошибки LNK1306.  
  
```cpp  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```  
  
Чтобы устранить эту проблему, не используйте параметр/CLR для скомпилируйте этот файл, или используйте `#pragma` директиву, чтобы поместить определение точки входа в неуправляемый раздел, как показано в следующем примере:  
  
```cpp  
// LNK1306fix.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
#include <windows.h>  
#pragma managed(push, off)  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
#pragma managed(pop)  
```  
