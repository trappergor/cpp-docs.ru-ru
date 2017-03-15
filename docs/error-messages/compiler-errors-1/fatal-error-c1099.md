---
title: "Неустранимая ошибка C1099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1099"
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Механизм "Изменить и продолжить" прервал компиляцию  
  
 Компонент "Изменить и продолжить" загрузил предварительно скомпилированный файл заголовка при подготовке к компиляции изменений кода, но последующие действия \(например, изменения кода до оператора предварительно скомпилированного заголовка `#include` или остановка отладчика\) помешали компоненту "Изменить и продолжить" завершить компиляцию в этом процессе. Не нужно предпринимать никаких действий, чтобы устранить эту ошибку.