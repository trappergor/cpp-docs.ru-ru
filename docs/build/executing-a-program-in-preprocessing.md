---
title: "Выполнение программ в ходе предварительной обработки | Microsoft Docs"
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
helpviewer_keywords: 
  - "выполнение программы [C++]"
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Выполнение программ в ходе предварительной обработки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Чтобы использовать код выхода команды во время предварительной обработки, следует заключить команду с любыми аргументами в квадратные скобки \(\[ \]\).  Все макросы расширяются до выполнения команды.  NMAKE замещает определение команды кодом выхода команды, который можно использовать в выражении для управления ходом предварительной обработки.  
  
## См. также  
 [Выражения в предобработке файлов makefile](../build/expressions-in-makefile-preprocessing.md)