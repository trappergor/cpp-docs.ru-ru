---
title: "EXTERNDEF | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EXTERNDEF
dev_langs: C++
helpviewer_keywords: EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a06378b7cf1217c01f57d7994220bfe5dd585a66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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