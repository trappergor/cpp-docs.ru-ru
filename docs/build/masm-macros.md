---
title: "Макросы MASM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 043ad96ada12467ce9c2ff39c9e337e0da9d2391
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="masm-macros"></a>Макросы MASM
Чтобы упростить использование [Необработанные псевдооперации](../build/raw-pseudo-operations.md), существует ряд макросы, определенные в файле ksamd64.inc, который можно использовать для создания типичных прологов и эпилогов.  
  
## <a name="remarks"></a>Примечания  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|alloc_stack(n)|Выделяет кадр стека n байт (с помощью sub rsp, n) и создает соответствующую раскрутки сведения (.allocstack n)|  
|save_reg reg, loc|Сохраняет reg защищенный регистр в стеке по RSP-loc смещения и помещает соответствующую информацию для раскрутки. (.savereg reg, loc)|  
|push_reg reg|Помещает в стек reg защищенный регистр и помещает соответствующую информацию для раскрутки. (.pushreg reg)|  
|rex_push_reg reg|Сохраняет защищенный регистр в стеке, с помощью извещающей 2 байт и создает соответствующую раскрутки сведения (.pushreg reg), он должен использоваться при первой инструкции в функции, чтобы убедиться, что функция является исправлять принудительной отправки.|  
|save_xmm128 reg, loc|Сохраняет reg энергонезависимого регистра XMM в стеке по RSP-loc смещения и помещает соответствующую информацию (.savexmm128 reg, loc) для раскрутки|  
|Смещение set_frame reg|Задает reg регистра кадра быть RSP + смещение (используя функцию mov или ОС) и создает соответствующую информацию (.set_frame reg, смещение) для раскрутки|  
|push_eflags|Помещает eflags с помощью команды pushfq и помещает соответствующую информацию (".alloc_stack 8") для раскрутки|  
  
 Ниже приведен пример пролога функции правильное использование макросов.  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
SavedRdi dq ?; saved register RDI   
SavedRsi dq ?; saved register RSI   
SkFrame ends  
  
sampleFrame struct  
Filldq?; fill to 8 mod 16  
SavedRdidq?; Saved Register RDI   
SavedRsi  dq?; Saved Register RSI  
sampleFrame ends  
  
sample2 PROC FRAME  
alloc_stack(sizeof sampleFrame)  
save_reg rdi, sampleFrame.SavedRdi  
save_reg rsi, sampleFrame.SavedRsi  
.end_prolog  
  
; function body  
  
mov rsi, sampleFrame.SavedRsi[rsp]  
mov rdi, sampleFrame.SavedRdi[rsp]  
  
; Here’s the official epilog  
  
add rsp, (sizeof sampleFrame)  
ret  
sample2 ENDP  
```  
  
## <a name="see-also"></a>См. также  
 [Вспомогательные процедуры раскрутки для MASM](../build/unwind-helpers-for-masm.md)