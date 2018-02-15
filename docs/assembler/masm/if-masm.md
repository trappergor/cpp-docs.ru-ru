---
title: "ЕСЛИ (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 74d9d223d12164de6a908159eb0d44ea271b0be5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="if-masm"></a>IF (MASM)
Предоставляет сборки *ifstatements* Если *expression1* имеет значение true (ненулевое) или *elseifstatements* Если *expression1* имеет значение false (0) и *expression2* имеет значение true.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## <a name="remarks"></a>Примечания  
 Следующие директивы может быть замещен [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, и **ELSEIFNDEF** . При необходимости выполняет сборку *elsestatements* Если предыдущее выражение имеет значение false. Обратите внимание, что выражения вычисляются во время сборки.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)