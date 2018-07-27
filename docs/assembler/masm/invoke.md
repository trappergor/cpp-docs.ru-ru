---
title: ВЫЗВАТЬ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27c18c83b623ce1a22ffcb5e1a9f1ce98ee6eb20
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055174"
---
# <a name="invoke"></a>INVOKE
Вызывает процедуру по адресу, заданному по *выражение*, передавая аргументы в стек или в регистрах, в соответствии с стандартные соглашения о вызовах языка типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## <a name="remarks"></a>Примечания  
 Каждый аргумент, передаваемый процедуре может быть выражение, выражение адреса или паре регистров (предшествует выражение `ADDR`).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)