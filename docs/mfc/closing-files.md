---
title: "Закрытие файлов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "файлы [C++], закрытие"
  - "MFC [C++], файловые операции"
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Закрытие файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Как правило, в операциях ВВОДА\-ВЫВОДА, после завершения с файлом необходимо закрыть его.  
  
#### Закрыть файл  
  
1.  Используйте функции\-члена **Закрыть**.  Эта функция закрывает файл файловой системы и буферы притоков соответственно.  
  
 При выборе объект [CFile](../mfc/reference/cfile-class.md) в кадре \(как показано в примере, приведенном в [Открытие файлов](../Topic/Opening%20Files.md)\), объект будет автоматически закрыт и затем уничтожается при выходит за пределы области действия.  Обратите внимание, что удаление объекта `CFile` не удаляет физический файл в файловой системе.  
  
## См. также  
 [Файлы](../mfc/files-in-mfc.md)