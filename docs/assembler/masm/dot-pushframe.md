---
title: . PUSHFRAME | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .PUSHFRAME
dev_langs:
- C++
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66531207d21bb7e9e0c165db135f5a0c0d77e478
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="pushframe"></a>.PUSHFRAME
Приводит к возникновению ошибки `UWOP_PUSH_MACHFRAME` входа код очистки. Если необязательный `code` указан, операция очистки кода получает модификатор 1. В противном случае модификатор — 0.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.PUSHFRAME [code]  
```  
  
## <a name="remarks"></a>Примечания  
 . PUSHFRAME позволяет пользователям указать, каким образом функция кадра освобождает ml64.exe и разрешено только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директивы. Эти директивы не создают код; только создать `.xdata` и `.pdata`. . PUSHFRAME должно предшествовать инструкции, которые фактически реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе чтобы соглашение.  
  
 Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)