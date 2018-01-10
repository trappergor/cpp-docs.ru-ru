---
title: "COMM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMM
dev_langs: C++
helpviewer_keywords: COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad12de948227f98ec73f779030b8e644dfad8b2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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