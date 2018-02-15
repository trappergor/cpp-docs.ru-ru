---
title: "ПСЕВДОНИМ (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Alias
dev_langs:
- C++
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1487afc250646b5cf1a12673dd43f6b1996a4f0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="alias-masm"></a>ALIAS (MASM)
**ПСЕВДОНИМ** директива создает альтернативное имя для функции.  Это позволяет создать несколько имен для функции или библиотеки, позволяющие компоновщик (LINK.exe) для сопоставления с новой функции в старой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `actual-name`  
 Фактическое имя функции или процедуры.  Угловые скобки не требуется.  
  
 `alias`  
 Имя альтернативного или псевдоним.  Угловые скобки не требуется.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)