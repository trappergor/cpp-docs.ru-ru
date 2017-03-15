---
title: "Предупреждение компилятора C4746 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# Предупреждение компилятора C4746
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

часто доступ и '\<expression\>' \/volatile: \[ISO&#124;параметр госпожи\]; рассмотрим использование встроенных функций \_\_iso\_volatile\_load\/store.  
  
 C4746 выдается, если испаряющая переменная доступна непосредственно.  Предназначен для помощи разработчикам указывать расположение кода, затронутых конкретной испаряющей определенной в настоящее время \(моделью, можно управлять с помощью параметра компилятора [\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) \).  В частности, может быть полезно в поиск создаваемых компилятором барьеры памяти оборудования при \/volatile:ms.  
  
 Встроенные \_\_iso\_volatile\_load\/store можно использовать напрямую для получения испаряющая память, не распространяться действие политики на испаряющей моделью.  С помощью этих внутренних не активирует C4746.  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).