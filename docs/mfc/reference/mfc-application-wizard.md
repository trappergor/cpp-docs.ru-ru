---
title: мастер приложений MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 6949f136890e8274f225a49496b2eb1b8f78b6fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351836"
---
# <a name="mfc-application-wizard"></a>мастер приложений MFC

Мастер приложений MFC генерирует приложение, которое при компиляции реализует основные функции исполняемого приложения Windows (.exe). Стартовое приложение MFC включает в себя исходные файлы C's (.cpp), файлы ресурсов (.rc), файлы заголовка (.h) и файл проекта (.vcxproj). Код, генерируемый в этих стартовых файлах, основан на MFC.

> [!NOTE]
> В зависимости от выбранных вариантов мастер создает дополнительные файлы в проекте. Например, если вы выбираете **чувствительную к контексту справку** на странице [Расширенные возможности,](../../mfc/reference/advanced-features-mfc-application-wizard.md) мастер создает файлы, необходимые для компиляции файлов справки проекта. Для получения дополнительной информации о файлах, создаваемых мастером, см. [Типы файлов, созданные для проектов Visual Studio,](../../build/reference/file-types-created-for-visual-cpp-projects.md)и см. файл Readme.txt в проекте.

## <a name="overview"></a>Обзор

Эта страница мастера описывает текущие параметры приложения для создаваемого приложения MFC. По умолчанию мастер создает проект следующим образом:

- [Тип приложения, Мастер приложений MFC](../../mfc/reference/application-type-mfc-application-wizard.md)

  - Проект создается с помощью поддержки интерфейса с несколькими документами (MDI). Для получения дополнительной информации [см.](../../mfc/sdi-and-mdi.md)

  - Проект использует [архитектуру документа/просмотра](../../mfc/document-view-architecture.md).

  - Проект использует библиотеки Unicode.

  - Проект создан с использованием стиля проекта Visual Studio и позволяет поменять визуальный стиль.

  - Проект использует MFC в общем DLL. Для получения дополнительной информации, [см.](../../build/dlls-in-visual-cpp.md)

- [Поддержка комплексных документов, Мастер приложений MFC](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - Проект не обеспечивает поддержку сложных документов.

- [Строки шаблонов документов, Мастер приложений MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - Проект использует название проекта для строк шаблона шаблона документа по умолчанию.

- [Поддержка базы данных, Мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)

  - Проект не обеспечивает поддержку баз данных.

- [Функции пользовательского интерфейса, MFC Приложение Мастер](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - Проект реализует стандартные функции пользовательского интерфейса Windows, такие как меню системы, панель статусов, максимизируйте и минимизирует коробки, поле **About,** стандартную панель меню и панель инструментов для стыковки, а также детские кадры.

- [Расширенные функции, MFC Приложение Мастер](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - Проект поддерживает печать и предварительный просмотр печати.

  - Проект поддерживает элементы управления ActiveX. Для получения дополнительной [информации см.](../../mfc/sequence-of-operations-for-creating-activex-controls.md)

  - Проект не обеспечивает поддержку [автоматизации,](../../mfc/automation.md) [MAPI,](../../mfc/mapi-support-in-mfc.md) [Windows Sockets](../../mfc/windows-sockets-in-mfc.md)или Active Accessibility.

  - Проект поддерживает стыковочные панели **Explorer,** стыковочные панели **выходного** стыковки и стыковочного стекла **Свойств.**

- [Создаваемые классы, мастер приложений MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - Класс представления проекта происходит от [класса CView.](../../mfc/reference/cview-class.md)

  - Класс приложений проекта происходит от [класса CWinAppEx.](../../mfc/reference/cwinappex-class.md)

  - Класс документов проекта происходит от [класса CDocument](../../mfc/reference/cdocument-class.md).

  - Основной класс кадров проекта происходит от [класса CMDIFrameWndEx.](../../mfc/reference/cmdiframewndex-class.md)

  - Класс детского кадра проекта происходит от [класса CMDIChildWndEx.](../../mfc/reference/cmdichildwndex-class.md)

Чтобы изменить эти параметры по умолчанию, щелкните соответствующее название вкладки в левой колонке мастера и внедвите изменения на отопавшей странице.

После создания проекта приложения MFC можно добавить объекты или элементы управления в проект с помощью [мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)Visual C.

## <a name="see-also"></a>См. также раздел

[Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md)<br/>
[Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)<br/>
[Использование классов для создания приложений для Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
