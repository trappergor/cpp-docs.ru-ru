---
title: Платформа (MFC) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87db7b28ec340a76c074a7b32c0e182030042eeb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381963"
---
# <a name="framework-mfc"></a>Платформа (MFC)

Данные с помощью платформы библиотеки Microsoft Foundation Class (MFC) зависит главным образом несколько основных классов и несколько инструментов Visual C++. Некоторые классы инкапсулируют большая часть интерфейс (API) Win32. Другие классы инкапсулируют концепции приложения, такие как документы, представления и само приложение. По-прежнему другие инкапсулировать OLE функции и возможности доступа к данным ODBC и DAO.

Например, Win32, концепция окно инкапсулируется класс MFC `CWnd`. То есть класс C++ с именем `CWnd` инкапсулирует или создает «оболочку» `HWND` дескриптор, представляющий окно Windows. Аналогично, класс `CDialog` инкапсулирует диалоговых окон Win32.

Инкапсуляция означает, что класс C++ `CWnd`, например, содержит переменную-член типа `HWND`, и функции-члены класса инкапсулируют вызовы функций Win32, которые принимают `HWND` как параметр. Функции-члены класса обычно имеют имя, совпадающее с именем функции Win32, которые они инкапсулируют.

## <a name="in-this-section"></a>В этом разделе

[SDI и MDI](../mfc/sdi-and-mdi.md)

[Документы, представления и платформа](../mfc/documents-views-and-the-framework.md)

[Мастера и редакторы ресурсов](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>Содержание смежных разделов

[Сборка в платформе](../mfc/building-on-the-framework.md)

[Вызовы кода со стороны платформы](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)

[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)

[Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)

[Объекты окон](../mfc/window-objects.md)

## <a name="see-also"></a>См. также

[Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
