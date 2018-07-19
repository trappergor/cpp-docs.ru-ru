---
title: EXTERNDEF | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b010f52f91a04388f34052fcc5c374690cff13df
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052704"
---
# <a name="externdef"></a>EXTERNDEF
Определяет один или несколько внешних переменных, меток или символов, которые называются *имя* , тип которого является `type`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## <a name="remarks"></a>Примечания  
 Если *имя* определяется в модуле, она обрабатывается как [ОТКРЫТЫЙ](../../assembler/masm/public-masm.md). Если *имя* имеется ссылка в модуле, она обрабатывается как [EXTERN](../../assembler/masm/extern-masm.md). Если *имя* — ссылки нет, он обрабатывается. `type` Может быть [ABS](../../assembler/masm/operator-abs.md), которая импортирует *имя* как константа. Обычно используется в включаемых файлов.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)