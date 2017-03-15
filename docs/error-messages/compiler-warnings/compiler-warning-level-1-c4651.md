---
title: "Предупреждение компилятора (уровень 1) C4651 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4651"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4651"
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4651
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

параметр "определение" указан для предкомпилированного заголовка, но не для текущей компиляции  
  
 Параметр "определение" был указан во время создания предкомпилированного заголовка, но не в этой компиляции.  
  
 Параметр "определение" будет использоваться в предкомпилированном заголовке, но не в остальной части кода.  
  
 Если предкомпилированный заголовок был построен с помощью \/DSYMBOL, компилятор выдаст предупреждение в случае, если в параметре компилятора \/Yu отсутствует значение \/DSYMBOL.  Данное предупреждение можно устранить, добавив в командную строку \/Yu значение \/DSYMBOL.