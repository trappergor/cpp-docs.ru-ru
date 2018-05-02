---
title: . DOSSEG | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3817cfe98758faf86ea87d74e02657598c3e806b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dosseg"></a>.DOSSEG
Упорядочивает сегменты в соответствии с соглашением сегмент MS-DOS: код сначала затем сегментов не в DGROUP, а затем сегменты в DGROUP.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>Примечания  
 Сегменты в DGROUP выполняйте в указанном порядке: сегменты без BSS или СТЕК, а затем BSS сегментов и наконец сегменты стека. В основном используется для обеспечения поддержки CodeView в изолированных программ MASM. То же, что [DOSSEG](../../assembler/masm/dosseg.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)