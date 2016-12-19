---
title: "Предупреждение компилятора (уровень 1) C4711 | Microsoft Docs"
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
  - "C4711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4711"
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция "функция" выбрана для подстановки  
  
 Компилятор выполнил подстановку кода указанной функции, хотя она и не была помечена как подставляемая.  
  
 Предупреждение C4711 включается, если указан параметр [\/Ob2](../../build/reference/ob-inline-function-expansion.md).  
  
 Встраивание кода выполняется компилятором автоматически.  Это предупреждение является информационным.  
  
 Данное предупреждение по умолчанию отключено.  Чтобы его включить, следует использовать прагма\-директиву [\#pragma warning](../../preprocessor/warning.md).  Дополнительные сведения см. в разделе [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).