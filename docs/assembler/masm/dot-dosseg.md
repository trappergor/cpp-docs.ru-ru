---
title: ". DOSSEG | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .DOSSEG
dev_langs: C++
helpviewer_keywords: .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a53159911c47d1c88df90c53f3302f813e5bd95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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