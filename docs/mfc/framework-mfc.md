---
title: "Платформа (MFC) | Microsoft Docs"
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
  - "API - интерфейсы [C++], инкапсуляция MFC Win32"
  - "платформа приложения [C++], о платформе приложений MFC"
  - "инкапсулированный API Win32"
  - "инкапсуляция [C++]"
  - "инкапсуляция [C++], API Win32"
  - "MFC [C++], платформа приложения"
  - "Win32 [C++], инкапсуляция API MFC"
  - "Windows API [C++], инкапсуляция MFC"
  - "классы-оболочки, проясняются"
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Платформа (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для работы с платформой библиотеки Microsoft Foundation Class \(MFC\) в большинстве основан на несколько основных классов и нескольких средств Visual C C\+\+.  Некоторые классы инкапсулируют большую часть программного интерфейса Win32 \(API\).  Другие классы инкапсулируют понятия приложения, такие как документы, представления и само приложение.  По\-прежнему инкапсулируют другие функции OLE функций и доступа к данным DAO и ODBC.  
  
 Например, структура Win32 окна инкапсулируется классом `CWnd` MFC.  То есть C\+\+ `CWnd` вызывается классом инкапсулирует или «создать» дескриптор `HWND`, представляющий окно Windows.  Кроме того, класс `CDialog` инкапсулирует диалоговые окна Win32.  
  
 Инкапсуляция означает, что класс `CWnd` C\+\+, например содержит переменную\-член типа `HWND` и функции\-члены класса инкапсулируют вызовы функций Win32, которые принимают в качестве параметра. `HWND` Функции\-члена класса обычно имеют то же имя, что и функция Win32 их инкапсулирует.  
  
## Содержание  
 [SDI и MDI](../mfc/sdi-and-mdi.md)  
  
 [Документы, представления и .NET Framework](../mfc/documents-views-and-the-framework.md)  
  
 [Мастера, редакторы ресурсов](../Topic/Wizards%20and%20the%20Resource%20Editors.md)  
  
## В соответствующих разделах  
 [Построение на платформе .NET Framework](../mfc/building-on-the-framework.md)  
  
 [Как .NET Framework вызывает исправление кода](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: Класс приложения](../Topic/CWinApp:%20The%20Application%20Class.md)  
  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [Обработка сообщений и сопоставление](../mfc/message-handling-and-mapping.md)  
  
 [Объекты окна](../mfc/window-objects.md)  
  
## См. также  
 [Использование классов для создания приложений для Windows](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)