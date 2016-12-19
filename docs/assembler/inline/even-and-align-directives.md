---
title: "Директивы EVEN и ALIGN | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "align"
  - "EVEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIGN - директива"
  - "директивы, MASM"
  - "EVEN - директива"
  - "MASM (макроассемблер Майкрософт), директивы"
  - "NOP (без инструкции операции)"
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Директивы EVEN и ALIGN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 Хотя встроенный ассемблер не поддерживает большинство директив MASM, он поддерживает директивы `EVEN` и **ALIGN**.  Эти директивы помещают инструкции **NOP** \(без операции\) в код сборки, если это нужно для выравнивания меток относительно определенных границ.  В результате для некоторых процессоров операции поиска инструкций выполняются более эффективно.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Использование языка ассемблера в блоках \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)