---
title: "Платформа (MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 09be7a5efbf3f78aa3cbc1862b811fff3d487c75
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="framework-mfc"></a>Платформа (MFC)
Работы с платформой библиотеки Microsoft Foundation Class (MFC) является главным образом на основе несколько основных классов и несколько средств Visual C++. Некоторые классы инкапсулируют большая часть интерфейса (API) Win32. Другие классы инкапсулируют понятий приложений, таких как документы, представления и само приложение. По-прежнему другие инкапсулируют OLE функции и возможности доступа к данным ODBC и DAO.  
  
 Например, Win32 понятие окна инкапсулируется класса MFC `CWnd`. То есть класс C++ вызывается `CWnd` инкапсулирует или создает «оболочку» `HWND` дескриптор, представляющий окно Windows. Аналогично, класс `CDialog` инкапсулирует диалоговых окон Win32.  
  
 Инкапсуляция означает, что класс C++ `CWnd`, например, содержит переменную-член типа `HWND`, и функции-члены класса инкапсулируют вызовы функций Win32, которые принимают `HWND` как параметр. Функции-члены класса, обычно имеют имя, совпадающее с именем функции Win32, в которую они инкапсулируют.  
  
## <a name="in-this-section"></a>Содержание  
 [SDI и MDI](../mfc/sdi-and-mdi.md)  
  
 [Документы, представления и платформа](../mfc/documents-views-and-the-framework.md)  
  
 [Мастера и редакторы ресурсов](../mfc/wizards-and-the-resource-editors.md)  
  
## <a name="in-related-sections"></a>Связанные разделы  
 [Сборка в платформе](../mfc/building-on-the-framework.md)  
  
 [Вызовы кода со стороны платформы](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)  
  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)  
  
 [Объекты окон](../mfc/window-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
