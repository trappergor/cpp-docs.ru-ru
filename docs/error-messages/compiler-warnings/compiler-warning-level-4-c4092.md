---
title: "Предупреждение компилятора (уровень 4) C4092 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4092"
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof возвращает "unsigned long"  
  
 Операнд оператора `sizeof` имеет очень большой размер, поэтому `sizeof` вернул unsigned **long**.  Это предупреждение возникает при использовании расширений Майкрософт \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  В режиме совместимости с ANSI \(\/Za\) результат вместо этого обрезается.