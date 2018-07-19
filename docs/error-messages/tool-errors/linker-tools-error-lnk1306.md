---
title: Ошибка средств компоновщика LNK1306 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb340a4c28f94f18e0c4b65bea8749394e002bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300502"
---
# <a name="linker-tools-error-lnk1306"></a>Ошибка средств компоновщика LNK1306  
  
> Функция точки входа библиотеки DLL не может управляться; откомпилируйте в машинный код  
  
`DllMain` Невозможно скомпилировать в MSIL-код; его необходимо скомпилировать в машинный код.  
  
Чтобы устранить эту проблему  
  
-   Скомпилируйте файл, содержащий точку входа без **/CLR**.  
  
-   Поместите точку входа `#pragma unmanaged` раздела.  
  
Дополнительные сведения:  
  
-   [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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
