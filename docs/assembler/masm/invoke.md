---
title: "ВЫЗВАТЬ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4876fa0a6e63addf529e7c458e052aff77ebc6a1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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