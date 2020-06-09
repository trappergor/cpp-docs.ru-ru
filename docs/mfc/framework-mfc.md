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
ms.openlocfilehash: b02d5a1862a278f46591895f20f58a97367b5ab2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618787"
---
# <a name="framework-mfc"></a>Платформа (MFC)

Работа с инфраструктурой библиотеки Microsoft Foundation Class (MFC) основана на нескольких основных классах и нескольких Visual C++ных инструментах. Некоторые классы инкапсулируют большую часть прикладного программного интерфейса (API) Win32. Другие классы инкапсулируют концепции приложений, такие как документы, представления и само приложение. Все еще другие инкапсулируют функции OLE и функции доступа к данным ODBC и DAO.  (DAO поддерживается в Office 2013. DAO 3,6 — это окончательная версия, которая считается устаревшей.)

Например, Win32's Концепция Window инкапсулируется классом MFC `CWnd` . То есть класс C++ с именем `CWnd` инкапсулирует или заключает в оболочку `HWND` , представляющую окно Windows. Аналогичным образом, класс `CDialog` инкапсулирует диалоговые окна Win32.

Инкапсуляция означает, что класс C++ `CWnd` , например, содержит переменную-член типа `HWND` , а функции-члены класса инкапсулируют вызовы функций Win32, которые принимают в `HWND` качестве параметра. Функции члена класса обычно имеют то же имя, что и функция Win32, которую они инкапсулируют.

## <a name="in-this-section"></a>В этом разделе

[SDI и MDI](sdi-and-mdi.md)

[Документы, представления и платформа](documents-views-and-the-framework.md)

[Мастера и редакторы ресурсов](wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>Содержание смежных разделов

[Сборка на платформе](building-on-the-framework.md)

[Вызовы кода со стороны платформы](how-the-framework-calls-your-code.md)

[CWinApp: класс приложений](cwinapp-the-application-class.md)

[Шаблоны документов и процесс создания документа/представления](document-templates-and-the-document-view-creation-process.md)

[Обработка и сопоставление сообщений](message-handling-and-mapping.md)

[Объекты окна](window-objects.md)

## <a name="see-also"></a>См. также раздел

[Использование классов для создания приложений для Windows](using-the-classes-to-write-applications-for-windows.md)
