---
title: "COMM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6258a584d39f598b32c43affc0ef2569b77b2047
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="comm"></a>COMM
Создает переменную общих с атрибутами, заданными в `definition`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Примечания  
 Каждый `definition` имеет следующий вид:  
  
 [[*langtype*]] [[**NEAR** &#124; **ДАЛЬНЕГО**]] *метка***:**`type`[[**:***число*]]  
  
 *Метка* имя переменной. `type` Может быть любым описателем типа ([БАЙТОВ](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)и так далее) или целое число, указывающее число байтов. *Число* указывает число объектов данных (одно значение по умолчанию).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)