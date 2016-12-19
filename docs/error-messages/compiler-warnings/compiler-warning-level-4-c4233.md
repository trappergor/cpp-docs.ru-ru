---
title: "Предупреждение компилятора (уровень 4) C4233 | Microsoft Docs"
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
  - "C4233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4233"
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение : ключевое слово "ключевоеслово" поддерживается только в C\+\+, но не в C  
  
 Исходный код компилируется как код C, а не C\+\+, но в нем используется ключевое слово, допустимое только в C\+\+.  Исходный код компилируется как код C, если исходный файл имеет расширение C, или же если используется параметр [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).  
  
 Данное предупреждение автоматически переходит в разряд ошибки.  Для устранения этого состояния следует использовать предупреждение директивы [\#pragma](../../preprocessor/warning.md).  Например, чтобы преобразовать предупреждение C4233 в предупреждение уровня 4, необходимо использовать директиву  
  
```  
#pragma warning(2:4233)  
```  
  
 в файле исходного кода.