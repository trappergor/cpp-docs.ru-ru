---
title: "Ссылки на сегменты во встроенной сборке | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "встроенная сборка, регистры"
  - "встроенная сборка, ссылки сегментов"
  - "ссылки, встроенная сборка"
  - "регистры"
  - "регистры, встроенная сборка"
  - "ссылки сегментов во встроенной сборке"
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ссылки на сегменты во встроенной сборке
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 Ссылаться на сегменты следует по регистру, а не по имени \(например, имя сегмента `_TEXT` недопустимо\).  В переопределениях сегментов необходимо явно использовать регистр, как в ES:\[BX\].  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Использование языка ассемблера в блоках \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)