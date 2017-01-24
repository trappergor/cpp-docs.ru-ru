---
title: "Использование стека | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Использование стека
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Все адреса памяти, лежащие вне текущего адреса RSP, считаются временными. Во время действия обработчика прерываний или выполнения пользовательского сеанса отладки эти адреса могут перезаписываться с помощью функций операционной системы или отладчика.  Таким образом, перед чтением значений из кадра стека или записью в него, необходимо задать RSP.  
  
 В этом разделе описывается порядок выделения памяти для локальных переменных в стеке, а также встроенная функция **alloca**.  
  
-   [Выделение памяти в стеке](../build/stack-allocation.md)  
  
-   [Динамическое создание параметра области стека](../Topic/Dynamic%20Parameter%20Stack%20Area%20Construction.md)  
  
-   [Типы функций](../build/function-types.md)  
  
-   [Выравнивание с помощью функции malloc](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## См. также  
 [Программные соглашения x64](../build/x64-software-conventions.md)