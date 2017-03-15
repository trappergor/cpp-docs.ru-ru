---
title: "Прочие выходные данные LIB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "выходные файлы, LIB"
ms.assetid: 656864a6-0b7a-4633-8dc6-ee3b1766d836
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Прочие выходные данные LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В режиме по умолчанию можно использовать параметр \/LIST для отображения сведений о результирующей библиотеке.  Можно перенаправить эти выходные данные в файл.  
  
 LIB выводит сообщение, содержащее сведения о версии и авторских правах, а также выводит файлы команд, если только не используется параметр \/NOLOGO.  
  
 При вводе только `lib`, LIB отображает оператор использования, группирующий параметры.  
  
 Сообщения об ошибке и предупреждения, выводимые LIB, имеют форму LNK*nnnn*.  Инструменты LINK, DUMPBIN и EDITBIN также используют этот диапазон ошибок.  Доступ к справке можно получить, выбрав соответствующую ошибку в окне вывода и нажав F1.  
  
## См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)