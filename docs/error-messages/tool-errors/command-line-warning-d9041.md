---
title: "Предупреждение командной строки D9041 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9041"
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение командной строки D9041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимое значение "значение" для "\/параметр"; предполагается "значение"; при указании этого предупреждения добавьте "\/analyze" в параметры командной строки  
  
 Номер предупреждения анализа кода был добавлен в параметр командной строки **\/wd**, **\/we**, **\/wo** или **\/wl** без указания параметра командной строки **\/analyze**.  Чтобы устранить данную ошибку, следует либо добавить параметр командной строки **\/analyze**, либо удалить недопустимый номер предупреждения из соответствующего параметра командной строки **\/w**.  
  
## Пример  
 Следующий пример командной строки приводит к появлению предупреждения D9041:  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Чтобы устранить предупреждение, добавьте параметр командной строки **\/analyze**.  Если параметр **\/analyze** не поддерживается версией компилятора, удалите недопустимый номер предупреждения из параметра **\/wd**.  
  
## См. также  
 [Ошибки командной строки с D8000 по D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)