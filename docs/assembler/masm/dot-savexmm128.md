---
title: . SAVEXMM128 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d50d4bbc7f9c89e9ef36a1dd8cf3dfeb56de79b5
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="savexmm128"></a>.SAVEXMM128
Приводит к возникновению ошибки либо `UWOP_SAVE_XMM128` или `UWOP_SAVE_XMM128_FAR` очистки запись для указанного регистра XMM и смещения, используя текущее смещение в прологе. MASM выберет наиболее эффективную кодировку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>Примечания  
 . SAVEXMM128 позволяет пользователям ml64.exe указать освобождает функция кадра и разрешено только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директивы. Эти директивы не создают код; только создать `.xdata` и `.pdata`. . SAVEXMM128 должно предшествовать инструкции, которые фактически реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе чтобы соглашение.  
  
 `offset` должно быть кратным 16.  
  
 Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)