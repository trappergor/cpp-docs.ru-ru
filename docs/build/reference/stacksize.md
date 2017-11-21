---
title: "STACKSIZE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: STACKSIZE
dev_langs: C++
helpviewer_keywords: STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82b33d217e593a35b66bb3530840a739e93082ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="stacksize"></a>STACKSIZE
Задает размер стека (в байтах).  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>Примечания  
 — Можно задать стек с [выделение памяти в стеке](../../build/reference/stack-stack-allocations.md) (/ STACK) параметра. См. в документации на соответствующий параметр подробные сведения *зарезервировать* и `commit` аргументы.  
  
 Этот параметр не оказывает влияния на библиотеки DLL.  
  
## <a name="see-also"></a>См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)