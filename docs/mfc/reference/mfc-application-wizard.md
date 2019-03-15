---
title: мастер приложений MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 808e8364764dd826ee82e445627ba21b06946ed6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822669"
---
# <a name="mfc-application-wizard"></a>мастер приложений MFC

Мастер приложений MFC создает приложения, при компиляции, реализует базовые возможности приложения Windows исполняемый файл (.exe). Начальное приложение MFC включает в себя (.cpp) исходные файлы C++, файлы ресурсов (.rc), файлы заголовков (.h) и файл проекта (VCXPROJ-файл). Код, созданный в этих файлах starter зависит от MFC.

> [!NOTE]
>  В зависимости от выбранных параметров мастер создает дополнительные файлы в проекте. Например, если вы выберите **контекстной справки** на [дополнительные функции](../../mfc/reference/advanced-features-mfc-application-wizard.md) страницы, мастер создает файлы, необходимые для компиляции файлов справки проекта. Дополнительные сведения о файлах, создаваемых мастером, см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../build/reference/file-types-created-for-visual-cpp-projects.md)и содержатся в файле Readme.txt в проекте.

## <a name="overview"></a>Обзор

На этой странице мастера описываются текущие параметры приложения для приложения MFC, которое вы создаете. По умолчанию мастер создает проект следующим образом:

- [Тип приложения, мастер приложений MFC](../../mfc/reference/application-type-mfc-application-wizard.md)

   - Создается проект с поддержкой с вкладками многодокументного интерфейса (MDI). Дополнительные сведения см. в разделе [SDI и MDI](../../mfc/sdi-and-mdi.md).

   - В проекте используется [архитектуры Document/View](../../mfc/document-view-architecture.md).

   - В проекте используются библиотеки Юникода.

   - Проект создается с использованием стиля проекта Visual Studio и включает смену визуального стиля.

   - Проект использует MFC в общей DLL. Дополнительные сведения см. в статье [DLL в Visual C++](../../build/dlls-in-visual-cpp.md).

- [Поддержка составных документов, мастер приложений MFC](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

   - Проект не поддерживает составных документов.

- [Страница "Строки шаблонов документов" мастера приложений MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

   - В проекте используется имя проекта, для строки шаблонов документов по умолчанию.

- [Поддержка базы данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)

   - Проект не поддерживает базы данных.

- [Параметры пользовательского интерфейса, мастер приложений MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

   - Этот проект реализует стандартный Windows, пользовательский интерфейс такие возможности, как системное меню, строка состояния, максимально увеличить и свести к минимуму полях **о** поле, стандартные строка меню и закрепления панели инструментов и дочерних фреймов.

- [Страница "Дополнительные возможности" мастера приложений MFC](../../mfc/reference/advanced-features-mfc-application-wizard.md)

   - Проект поддерживает печати и предварительного просмотра.

   - Проект поддерживает элементы управления ActiveX. Дополнительные сведения см. в разделе [последовательность операций для создания элементов управления ActiveX](../../mfc/sequence-of-operations-for-creating-activex-controls.md).

   - Проект не поддерживает [автоматизации](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), или в Active Accessibility.

   - Проект поддерживает **Explorer** закрепляемой области **вывода** закрепляемой области и **свойства** закрепляемой области.

- [Создаваемые классы, мастер приложений MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md)

   - Класс представления проекта является производным от [CView Class](../../mfc/reference/cview-class.md).

   - Класс приложения проекта является производным от [класс CWinAppEx](../../mfc/reference/cwinappex-class.md).

   - Класс документа проекта является производным от [класс CDocument](../../mfc/reference/cdocument-class.md).

   - Класс главного фрейма проекта является производным от [класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md).

   - Класс фрейма дочернего проекта является производным от [класс CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md).

Чтобы изменить эти параметры по умолчанию, щелкните соответствующую вкладку заголовок в левом столбце мастера и внесите изменения на появившейся странице.

После создания проекта приложения MFC, можно добавить объекты и элементы управления в проект с помощью Visual C++ [кода мастеров](../../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="see-also"></a>См. также

[Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md)<br/>
[Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)<br/>
[Использование классов для создания приложений для Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
