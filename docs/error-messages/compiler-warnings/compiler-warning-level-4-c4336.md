---
title: "Предупреждение (уровень 4) C4336 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4336
dev_langs: C++
helpviewer_keywords: C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2cbb27a524caf5c02cbc99d8792c93ecc134390a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4336"></a>Предупреждение компилятора (уровень 4) C4336
Импорт библиотеки «type_lib1» перекрестные перед импортом «type_lib2»  
  
 Библиотека типов была ссылка в [#import](../../preprocessor/hash-import-directive-cpp.md) директивы. Однако эта библиотека типов содержит ссылку на другую библиотеку типов, который не был указан с `#import`. TLB-файл другой найден компилятором.  
  
 Две указанные библиотеки типов создаются из следующих двух файлах (скомпилированный с midl.exe):  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 Второй библиотеки типов:  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 Следующий пример приводит к возникновению ошибки C4336:  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```