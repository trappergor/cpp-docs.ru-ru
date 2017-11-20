---
title: "ПСЕВДОНИМ (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Alias
dev_langs: C++
helpviewer_keywords: ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39f539c18ce23fb3ef9630e4bfdfca8f265beb33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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