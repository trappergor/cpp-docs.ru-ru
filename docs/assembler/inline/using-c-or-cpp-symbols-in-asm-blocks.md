---
title: "Использование символов C или C++ в блоках __asm | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6a39b747c8c576d148bafff19a664a95fcb43e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>Использование символов C или C++ в блоках __asm
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Блок `__asm` может обозначать любой символ C или C++ в той области видимости, в которой находится этот блок. (Символами C и C++ считаются имена переменных, имена функций и метки, то есть имена, которые не являются символьными константами или членами объекта `enum`. Вызов функций-членов C++ невозможен.)  
  
 На использование символов C и C++ накладывается несколько ограничений.  
  
-   Каждый оператор языка ассемблера может содержать только один символ C или C++. Несколько символов может находиться в той же инструкции ассемблера только с **длина**, **тип**, и **размер** выражения.  
  
-   Объявления (прототипы) функций, ссылки на которые находятся в блоке `__asm`, должны быть созданы в более ранней точке программы. В противном случае компилятор не может различать имена функций и метки, находящиеся в блоке `__asm`.  
  
-   Блок `__asm` не может использовать символы C или C++, совпадающие по написанию с зарезервированными словами MASM (вне зависимости от регистра). Зарезервированным словам MASM относятся имена инструкций, такие как **PUSH** и имена регистров, например SI.  
  
-   В блоках `__asm` не распознаются маркеры структуры и объединения.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)