---
title: "Ошибка средств компоновщика LNK2039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2039"
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ошибка средств компоновщика LNK2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

импортирование ссылочный класс '\<type\>', определенный в another.obj; он должен быть импортирован или указан, но не оба  
  
 Класс '\<`type`\>' ссылочного импортирован в определенном OBJ\-файле, но уже определен в другом OBJ\-файле.  Это условие может вызвать сбой среды выполнения или другое непредвиденное расширения функциональности.  
  
### Исправление этой ошибки  
  
1.  Убедитесь, '`type`' должен быть определен в другом файле и чеке OBJ ли его необходимо импортировать из файла .winmd.  
  
2.  Удалите или определение или импортировать.  
  
## См. также  
 [Ошибки и предупреждения инструментов компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [Ошибка средств компоновщика LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)