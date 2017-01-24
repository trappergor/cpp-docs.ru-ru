---
title: "буфер обмена | Microsoft Docs"
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
  - "буфер обмена"
  - "буфер обмена, программирование"
  - "копирование данных"
  - "вырезка и копирование данных"
  - "перенос данных"
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# буфер обмена
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это семейство статей объясняется, как реализовать поддержку обмена Windows в приложениях MFC.  Используется в буфер обмена Windows 2 двумя способами:  
  
-   Реализация стандартных команд меню " Правка, например, вырезать, копировать и вставлять.  
  
-   Реализация равномерную передачу данных с перетаскиванием OLE \(\).  
  
 Стандартный метод обмена Windows переноса данных между источником и назначением.  Также может быть удобно в операциях OLE.  С появлением OLE, 2 механизма буфера обмена в Windows.  Стандартное API обмена Windows по\-прежнему доступно, но был дополнен с OLE механизмом передачи данных.  OLE унифицированная передача данных \(UDT\) поддерживает вырезать, копировать и вставлять exchange и перетаскивания.  
  
 Обмен системная служба во всем сеансом Windows, поэтому он не имеет дескриптор или собственного класса.  Управление обмена с помощью функций\-членов класса [CWnd](../Topic/CWnd%20Class.md).  
  
## Дополнительные сведения  
  
-   [Когда использовать каждый из этих механизмов буфера обмена](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [Наряду с помощью API обмена Windows](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [Использование OLE механизм буфера обмена](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Копирование и вставящ данные](../Topic/Clipboard:%20Copying%20and%20Pasting%20Data.md)  
  
-   [Добавить другие форматы](../mfc/clipboard-adding-other-formats.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="1bc8aafd7da110d0b343b54cffa169d9" class\="tgtSentence"\>Обмена Windows\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms648709)  
  
-   [Реализация перетаскивания OLE \(\)](../mfc/drag-and-drop-ole.md)  
  
## См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)