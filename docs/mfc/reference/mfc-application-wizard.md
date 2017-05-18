---
title: "Мастер приложений MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2d1d950ac5adb5d17b172fa058a40593e4e61c34
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-application-wizard"></a>мастер приложений MFC
Мастер приложений MFC создает приложение, в скомпилированном виде реализует базовые возможности приложения Windows, исполняемый файл (.exe). Начальное приложение MFC включает файлы C++ (.cpp) источника, файлы ресурсов (RC), файлы заголовков (h) и файл проекта (VCXPROJ). Код, созданный в этих начальных файлах, основан на MFC.  
  
> [!NOTE]
>  В зависимости от выбранных параметров мастер создает дополнительные файлы в проекте. Например, если выбрать **контекстной справки** на [дополнительные функции](../../mfc/reference/advanced-features-mfc-application-wizard.md) страницы, мастер создает файлы, необходимые для компиляции файлов справки проекта. Дополнительные сведения о файлах, создаваемых мастером в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md)и содержатся в файле Readme.txt в проекте.  
  
## <a name="overview"></a>Обзор  
 На этой странице мастера описываются текущие параметры приложения для создаваемого приложения MFC. По умолчанию мастер создает проект следующим образом:  
  
-   [Тип приложения, мастер приложений MFC](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   Проект создается с поддержкой с вкладками многодокументного интерфейса (MDI). Дополнительные сведения см. в разделе [SDI и MDI](../../mfc/sdi-and-mdi.md).  
  
    -   В проекте используется [архитектуры документ/представление](../../mfc/document-view-architecture.md).  
  
    -   В проекте используются библиотеки Юникод.  
  
    -   Проект создается с использованием стиля проекта Visual Studio и поддержкой переключения визуальных стилей.  
  
    -   Проект использует MFC в общей библиотеке DLL. Дополнительные сведения см. в разделе [библиотеки DLL в Visual C++](../../build/dlls-in-visual-cpp.md).  
  
-   [Поддержка составных документов, мастер приложений MFC](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   Проект не поддерживает составные документы.  
  
-   [Строки шаблонов документов, мастер приложений MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   Данный проект использует имя проекта для строки шаблонов документов по умолчанию.  
  
-   [Поддержка базы данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   Проект не поддерживает базы данных.  
  
-   [Возможности пользовательского интерфейса, мастер приложений MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   Проект реализует пользовательский интерфейс такие возможности, как главное меню, строка состояния, кнопки свертывания и развертывания окна, стандартная Windows **о** поле, стандартные строка меню и закрепления панели инструментов и дочерних фреймов.  
  
-   [Дополнительные возможности, мастер приложений MFC](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   Проект поддерживает печать и предварительный просмотр.  
  
    -   Проект поддерживает элементы управления ActiveX. Дополнительные сведения см. в разделе [последовательность операций для создания элементов управления ActiveX](../../mfc/sequence-of-operations-for-creating-activex-controls.md).  
  
    -   Проект не поддерживает [автоматизации](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), или Active Accessibility.  
  
    -   Проект поддерживает **Explorer** закрепляемой области **вывод** закрепляемой области и **свойства** закрепляемой области.  
  
-   [Создаваемые классы, мастер приложений MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   Класс представления проекта является производным от [CView-класс](../../mfc/reference/cview-class.md).  
  
    -   Класс приложения проекта является производным от [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
    -   Класс документа проекта является производным от [CDocument-класс](../../mfc/reference/cdocument-class.md).  
  
    -   Класс основного фрейма проекта является производным от [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md).  
  
    -   Класс дочернего фрейма проекта является производным от [класс CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md).  
  
 Чтобы изменить эти параметры по умолчанию, щелкните соответствующую вкладку заголовок в левом столбце мастера и внести изменения на появившейся странице.  
  
 После создания проекта приложения MFC, можно добавить объекты и элементы управления в проект Visual C++ с помощью [мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md)   
 [Настольных приложений MFC](../../mfc/mfc-desktop-applications.md)   
 [Использование классов для создания приложений для Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)

