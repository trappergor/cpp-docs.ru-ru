---
title: "ЕСЛИ (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b6ddb2c9d9ec6e39a0147d513fb452685d8e7213
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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