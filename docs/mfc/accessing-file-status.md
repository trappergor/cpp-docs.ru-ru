---
title: "Доступ к состоянию файла | Microsoft Docs"
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
  - "примеры [MFC], статус файла"
  - "статус файла [C++]"
  - "файлы [C++], доступ"
  - "файлы [C++], сведения о статусе"
  - "статус файлов"
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Доступ к состоянию файла
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CFile` также поддерживает получение состояния файла, включая, существует ли файл, создание и даты и времени изменений, логический размер и путь.  
  
### Чтобы получить состояние файла  
  
1.  Используйте класс [CFile](../mfc/reference/cfile-class.md) для получения и задания сведений о файле.  Одно полезное приложение использовать статический функции\-члена **GetStatus**`CFile`, чтобы определить, существует ли файл.  **GetStatus** возвращает 0, если указанный файл не существует.  
  
 Таким образом, необходимо использовать результат **GetStatus**, чтобы определить, можно ли использовать флажок **CFile::modeCreate** для файла, как показано в следующем примере.  
  
 [!code-cpp[NVC_MFCFiles#3](../mfc/codesnippet/CPP/accessing-file-status_1.cpp)]  
  
 Дополнительные сведения см. в разделе [Сериализация](../Topic/Serialization%20in%20MFC.md).  
  
## См. также  
 [Файлы](../mfc/files-in-mfc.md)