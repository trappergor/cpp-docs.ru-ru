---
title: ОПЕРАТОР GOTO (MASM) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecdab2fe91de0aae656b37c6fddafe658e60c0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="goto-masm"></a>GOTO (MASM)
Передает строку, помеченную сборки **: *** macrolabel*.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Оператор GOTO** разрешены только в [МАКРОС](../../assembler/masm/macro.md), [для](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [ПОВТОРИТЕ](../../assembler/masm/repeat.md), и **при**блоки. Метка должна быть только директивой в строке и должен предшествовать начальное двоеточие.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)