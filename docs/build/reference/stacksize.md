---
title: STACKSIZE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b2093762b3c6f21d319c53a85da5ec5b430a1fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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