---
title: Платформа (MFC)
ms.date: 09/17/2019
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
ms.openlocfilehash: 387f53e3123b6863fcf218da39c7c5e356eb8219
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303404"
---
# <a name="framework-mfc"></a>Платформа (MFC)

Работа с инфраструктурой библиотеки Microsoft Foundation Class (MFC) основана на нескольких основных классах и нескольких визуальных C++ средствах. Некоторые классы инкапсулируют большую часть прикладного программного интерфейса (API) Win32. Другие классы инкапсулируют концепции приложений, такие как документы, представления и само приложение. Все еще другие инкапсулируют функции OLE и функции доступа к данным ODBC и DAO.  (DAO поддерживается в Office 2013. DAO 3,6 — это окончательная версия, которая считается устаревшей.)

Например, Win32's концепция окна инкапсулируется классом MFC `CWnd`. То есть C++ класс, именуемый `CWnd`, инкапсулирует или заключает в оболочку `HWND`ный обработчик, представляющий окно Windows. Аналогичным образом класс `CDialog` инкапсулирует диалоговые окна Win32.

Инкапсуляция означает, что C++ класс `CWnd`, например, содержит переменную-член типа `HWND`, а функции-члены класса инкапсулируют вызовы функций Win32, которые принимают `HWND` в качестве параметра. Функции члена класса обычно имеют то же имя, что и функция Win32, которую они инкапсулируют.

## <a name="in-this-section"></a>В этом разделе

[SDI и MDI](../mfc/sdi-and-mdi.md)

[Документы, представления и платформа](../mfc/documents-views-and-the-framework.md)

[Мастера и редакторы ресурсов](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>В связанных разделах

[Сборка в платформе](../mfc/building-on-the-framework.md)

[Вызовы кода со стороны платформы](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)

[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)

[Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)

[Объекты окон](../mfc/window-objects.md)

## <a name="see-also"></a>См. также

[Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
