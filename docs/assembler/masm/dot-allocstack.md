---
title: ". ALLOCSTACK | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .ALLOCSTACK
dev_langs:
- C++
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f37fcabdae3e8b96670fed12d98cf9d0a2adcf63
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="allocstack"></a>.ALLOCSTACK
Приводит к возникновению ошибки **UWOP_ALLOC_SMALL** или **UWOP_ALLOC_LARGE** с указанным размером для текущее смещение в прологе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.ALLOCSTACK size  
```  
  
## <a name="remarks"></a>Примечания  
 MASM выберет наиболее эффективный кодировку для заданного размера.  
  
 . ALLOCSTACK позволяет пользователям указать, каким образом функция кадра освобождает ml64.exe и разрешено только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директивы. Эти директивы не создают код; только создать `.xdata` и `.pdata`. . ALLOCSTACK должно предшествовать инструкции, которые фактически реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе чтобы соглашение.  
  
 `size` Операнд должен быть кратен 8.  
  
 Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="sample"></a>Пример  
 Следующий пример показано, как задать обработчик очистки или исключение:  
  
```  
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console  
text SEGMENT  
PUBLIC Example3  
PUBLIC Example3_UW  
Example3_UW PROC NEAR  
   ; exception/unwind handler body  
  
   ret 0  
  
Example3_UW ENDP  
  
Example3 PROC FRAME : Example3_UW  
  
   sub rsp, 16  
.allocstack 16  
  
.endprolog  
  
   ; function body  
    add rsp, 16  
   ret 0  
  
Example3 ENDP  
text ENDS  
END  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)