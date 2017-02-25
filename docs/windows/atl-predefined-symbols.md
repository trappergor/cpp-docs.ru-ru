---
title: "ATL Predefined Symbols | Microsoft Docs"
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
  - "symbols, ATL predefined"
  - "ATL symbols"
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти символы определяются в файлах заголовков ATL, но они поддерживают стандартные функции и действия приложений Windows.  Данные символы как правило используются в диалоговых окнах.  При работе с элементами управления в диалоговых окнах и элементах управления эти символы появляются в [редакторе диалоговых окон](../mfc/dialog-editor.md), связанном с типичными элементами управления.  Например, если в диалоговом окне есть кнопка "Отменить", данная команда будет связана с символом IDCANCEL в [окне "Свойства"](../Topic/Properties%20Window.md).  
  
|||  
|-|-|  
|IDABORT|Элемент управления: кнопка диалогового окна "Прервать"|  
|IDC\_STATIC|Элемент управления: статический элемент управления|  
|IDCANCEL|Элемент управления: кнопка диалогового окна "Отмена"|  
|IDIGNORE|Элемент управления: кнопка диалогового окна "Пропустить"|  
|IDNO|Элемент управления: кнопка диалогового окна "Нет"|  
|IDOK|Элемент управления: кнопка диалогового окна "OK"|  
|IDR\_ACCELERATOR1|Ресурс: таблица сочетаний клавиш|  
|IDRETRY|Элемент управления: кнопка диалогового окна "Повторить"|  
|IDS\_PROJNAME|Строка: имя текущего приложения|  
|IDYES|Элемент управления: кнопка диалогового окна "Да"|  
  
## Требования  
 Библиотека ATL  
  
## См. также  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)