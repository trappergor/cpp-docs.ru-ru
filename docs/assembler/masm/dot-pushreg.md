---
title: ". PUSHREG | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .PUSHREG
dev_langs:
- C++
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84cc00d51f72993e1e7673d8d4f3d01478d32041
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="pushreg"></a>.PUSHREG
Приводит к возникновению ошибки `UWOP_PUSH_NONVOL` очистки записи кода для указанного номера с помощью текущего смещения в прологе зарегистрирован.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.PUSHREG register  
```  
  
## <a name="remarks"></a>Примечания  
 . PUSHREG позволяет пользователям ml64.exe указать освобождает функция кадра и разрешено только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директивы. Эти директивы не создают код; только создать `.xdata` и `.pdata`. . PUSHREG должно предшествовать инструкции, которые фактически реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе чтобы соглашение.  
  
 Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="sample"></a>Пример  
  
### <a name="description"></a>Описание:  
 Следующий пример демонстрирует push долговременного tegisters.  
  
### <a name="code"></a>Код  
  
```  
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
Example1 PROC FRAME  
   push r10  
.pushreg r10  
   push r15  
.pushreg r15  
   push rbx  
.pushreg rbx  
   push rsi  
.pushreg rsi  
.endprolog  
   ; rest of function ...  
   ret  
Example1 ENDP  
_text ENDS  
END  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)