---
title: ". PUSHFRAME | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .PUSHFRAME
dev_langs: C++
helpviewer_keywords: .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c10a6b92be86b3b5fc30d2975cb60cf211b026f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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