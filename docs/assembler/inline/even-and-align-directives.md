---
title: "Директивы EVEN и ALIGN | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- align
- EVEN
dev_langs:
- C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 278794e0105ee054fdd4948967a78982a9d46d8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="even-and-align-directives"></a>Директивы EVEN и ALIGN
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Хотя встроенный ассемблер не поддерживает большинство директив MASM, он поддерживает `EVEN` и **ВЫРОВНЯТЬ**. Эти директивы помещают **NOP** (без операции) инструкции в код сборки, необходимые для выравнивания меток относительно определенных границ. В результате для некоторых процессоров операции поиска инструкций выполняются более эффективно.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)