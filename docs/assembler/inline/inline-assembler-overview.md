---
title: "Общие сведения о встроенном ассемблере | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a58d9fd2dbce875c39c4c0e9af7ae85d5b20f43d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="inline-assembler-overview"></a>Обзор встроенного кода на ассемблере
**Блок, относящийся только к системам Microsoft**  
  
 Встроенный ассемблер позволяет внедрять инструкции языка ассемблера непосредственно в исходные программы С и С++ без дополнительных шагов по сборке и компоновке. Встроенный код на ассемблере встроен в компилятор, поэтому вам не требуется отдельный сборщик для языка ассемблера, такой как Microsoft Macro Assembler (MASM).  
  
 Так как встроенный ассемблер не требует отдельных действий по сборке и компоновке, он является более удобным, чем отдельный ассемблер. Во встроенном коде на языке ассемблера можно использовать любое имя переменной или функции языка C или C++, находящееся в области видимости, поэтому его легко интегрировать с кодом C и C++ программы. Поскольку в коде на языке ассемблера можно одновременно использовать операторы C или C++, с его помощью можно выполнять задачи, которые слишком сложно или невозможно выполнить только в C или только в C++.  
  
 [__Asm](../../assembler/inline/asm.md) ключевое слово вызывает встроенный ассемблер и может использоваться везде, где допустим оператор C или C++. Он не может отображаться самостоятельно. За ним должна следовать инструкция по сборке, группа инструкций, заключенная в круглые скобки, либо, в крайнем случае, пустая пара круглых скобок. Термин "блок `__asm`" в этом разделе относится к любой инструкции или группе инструкций, в скобках или без них.  
  
 Следующий код — это простой блок `__asm`, заключенный в фигурные скобки. (Этот код является последовательностью пролога пользовательской функции.)  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 Кроме того, можно поставить `__asm` перед каждой инструкцией по сборке.  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 Поскольку ключевое слово `__asm` является разделителем операторов, можно также помещать инструкции ассемблера на одной строке.  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенный сборщик](../../assembler/inline/inline-assembler.md)