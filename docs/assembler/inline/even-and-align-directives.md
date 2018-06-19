---
title: Директивы EVEN и ALIGN | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a43425a4038ffb140eeaa0a9d111a39fc5c11ff0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057959"
---
# <a name="even-and-align-directives"></a>Директивы EVEN и ALIGN
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Хотя встроенный ассемблер не поддерживает большинство директив MASM, он поддерживает `EVEN` и **ВЫРОВНЯТЬ**. Эти директивы помещают **NOP** (без операции) инструкции в код сборки, необходимые для выравнивания меток относительно определенных границ. В результате для некоторых процессоров операции поиска инструкций выполняются более эффективно.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)