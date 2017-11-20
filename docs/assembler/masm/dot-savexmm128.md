---
title: ". SAVEXMM128 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEXMM128
dev_langs: C++
helpviewer_keywords: .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4f79fc84e12f536383753d1d5982751cd30099d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="savexmm128"></a>.SAVEXMM128
Приводит к возникновению ошибки либо `UWOP_SAVE_XMM128` или `UWOP_SAVE_XMM128_FAR` очистки запись для указанного регистра XMM и смещения, используя текущее смещение в прологе. MASM выберет наиболее эффективную кодировку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>Примечания  
 . SAVEXMM128 позволяет пользователям ml64.exe указать освобождает функция кадра и разрешено только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директивы. Эти директивы не создают код; только создать `.xdata` и `.pdata`. . SAVEXMM128 должно предшествовать инструкции, которые фактически реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе чтобы соглашение.  
  
 `offset`должно быть кратным 16.  
  
 Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)