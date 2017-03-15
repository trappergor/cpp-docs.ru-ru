---
title: "Ошибка компилятора C3381 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3381"
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"сборка": спецификаторы доступа к сборке доступны только в коде, скомпилированном с параметром \/clr  
  
 Собственные типы могут быть видны вне сборки, но можно указать доступ к сборке для собственных типов только в компиляции **\/clr**.  
  
 Дополнительные сведения см. в разделах [Видимость типа](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3381.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```