---
title: "Ошибка средств компоновщика LNK1306 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1306"
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка средств компоновщика LNK1306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

точки входа в DLL "функция" не может быть управляемой; откомпилируйте в машинный код  
  
 Функция DllMain не может быть скомпилирована в MSIL. Она должна быть скомпилирована в машинный код.  
  
 Чтобы устранить данную ошибку,  
  
-   Скомпилируйте файл, содержащий точку входа, без использования **\/clr**.  
  
-   Поместите точку входа в раздел `#pragma unmanaged`.  
  
-   Дополнительные сведения см. в следующем разделе.  
  
-   [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed, unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [Инициализация смешанных сборок](../Topic/Initialization%20of%20Mixed%20Assemblies.md)  
  
-   [Поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md)  
  
## Пример  
 Следующий пример приводит к возникновению ошибки LNK1306.  
  
```  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```