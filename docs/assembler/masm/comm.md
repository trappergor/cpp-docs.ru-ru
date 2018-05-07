---
title: COMM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 111dac47089fea13febe787e5b73557b287beea8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="comm"></a>COMM
Создает переменную общих с атрибутами, заданными в `definition`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Примечания  
 Каждый `definition` имеет следующий вид:  
  
 [[*langtype*]] [[**NEAR** &#124; **ДАЛЬНЕГО**]] *метка ***:**`type`[[**:*** число*]]  
  
 *Метка* имя переменной. `type` Может быть любым описателем типа ([БАЙТОВ](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)и так далее) или целое число, указывающее число байтов. *Число* указывает число объектов данных (одно значение по умолчанию).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)