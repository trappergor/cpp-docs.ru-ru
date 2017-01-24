---
title: "Неустранимая ошибка C1383 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1383"
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр компилятора \/GL несовместим с установленной версией среды CRL  
  
 Ошибка C1383 происходит, когда вы используете предыдущую версию среды CLR с более новой версией компилятора и когда вы компилируете с параметрами **\/clr** и **\/GL.**  
  
 Для устранения этой ошибки не используйте параметры **\/GL** и **\/clr** или установите версию среды CLR, которая поставляется с вашим компилятором.  
  
 Дополнительные сведения см. в разделах [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) и [\/GL \(оптимизация всей программы\)](../../build/reference/gl-whole-program-optimization.md).