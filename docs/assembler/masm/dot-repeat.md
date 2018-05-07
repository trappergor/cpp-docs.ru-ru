---
title: . ПОВТОРИТЕ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .REPEAT
dev_langs:
- C++
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41e3dadaa95cb4bf0ca4a17af32332d5b5471245
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="repeat"></a>.REPEAT
Создает код, который повторяет выполнение блока *инструкций* до `condition` становится значение true. [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md), которая становится значение true, когда CX равно нулю, может быть замещен [. ПОКА](../../assembler/masm/dot-until.md). `condition` Необязателен с **. UNTILCXZ**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)