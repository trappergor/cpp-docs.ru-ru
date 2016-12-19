---
title: "Win32 Predefined Symbols | Microsoft Docs"
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
  - "Win32 [C++], predefined symbols"
  - "symbols, Win32 predefined"
  - "Windows API [C++], predefined symbols"
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти символы определяются в файлах заголовков Win32, и они поддерживают стандартные функции и действия приложений Windows.  Эти символы в основном используются вместе с типичными элементами пользовательского интерфейса.  При работе с элементами управления в редакторах ресурсов эти символы появляются в [окне "Свойства"](../Topic/Properties%20Window.md), связанном с типичными элементами управления.  Например, если панель инструментов должна отображать значок приложения, значок должен быть связан с символом IDI\_SMALL в окне "Свойства".  
  
|||  
|-|-|  
|IDABORT|Элемент управления: кнопка диалогового окна "Прервать"|  
|IDC\_STATIC|Элемент управления: надпись в диалоговом окне|  
|IDCANCEL|Элемент управления: кнопка диалогового окна "Отмена"|  
|IDD\_ABOUTBOX|Диалоговое окно: диалоговое окно "О продукте"|  
|IDI\_PROJECTNAME|Значок: значок текущего проекта|  
|IDI\_SMALL|Значок: маленький значок текущего проекта|  
|IDIGNORE|Элемент управления: используется вместе с кнопкой "Игнорировать" в диалоговых окнах|  
|IDM\_ABOUT|Пункт меню: используется вместе с "Справка...О программе..."|  
|IDM\_EXIT|Пункт меню: используется вместе с "Файл...Выход..."|  
|IDNO|Элемент управления: кнопка диалогового окна "Нет"|  
|IDOK|Элемент управления: кнопка диалогового окна "OK"|  
|IDRETRY|Элемент управления: кнопка диалогового окна "Повторить"|  
|IDS\_APP\_TITLE|Строка: имя текущего приложения|  
|IDYES|Элемент управления: кнопка диалогового окна "Да"|  
  
## Требования  
 Win32  
  
## См. также  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)