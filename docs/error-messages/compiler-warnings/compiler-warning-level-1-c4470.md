---
title: "Предупреждение (уровень 1) C4470 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4470
dev_langs: C++
helpviewer_keywords: C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e77fa078dd3263f796c7b136068e10567da3e0d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4470"></a>Предупреждение компилятора (уровень 1) C4470
директивы pragma контроля плавающей учитывается в/CLR  
  
 Типы директив pragma с плавающей точкой управления:  
  
-   [fenv_access](../../preprocessor/fenv-access.md)  
  
-   [float_control](../../preprocessor/float-control.md)  
  
-   [fp_contract](../../preprocessor/fp-contract.md)  
  
 не действуют в [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Следующий пример приводит к возникновению ошибки C4470:  
  
```  
// C4470.cpp  
// compile with: /clr /W1 /LD  
#pragma float_control(except, on)   // C4470  
```