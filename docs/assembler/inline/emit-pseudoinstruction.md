---
title: "псевдоинструкция _emit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c506c689b94a7f6f7fa51c4c456e20454b28df02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="emit-pseudoinstruction"></a>Псевдоинструкция _emit
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 **_Emit** pseudoinstruction определяет один байт в текущее положение в текущем сегменте текста. **_Emit** напоминает pseudoinstruction [DB](../../assembler/masm/db.md) директивой MASM.  
  
 В следующем примере в код помещаются байты 0x4A, 0x43 и 0x4B:  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  Если псевдокоманда `_emit` создает инструкции, которые изменяют регистры, а приложение компилируется с включенными оптимизациями, то компилятор не в состоянии определить, на какие регистры она действует. Например если `_emit` создает инструкцию, которая изменяет **rax** регистр, компилятор не знает, **rax** изменилось. Затем компилятор может сделать неверное допущение о значении этого регистра после выполнения встроенного кода на языке ассемблера. Поэтому запущенное приложение может работать непредсказуемым образом.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)