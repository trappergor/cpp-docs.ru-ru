---
title: "Мастер приложений MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.overview
dev_langs: C++
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0fac78eddcdf36ecc295841019f9e3f05e537802
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-application-wizard"></a>мастер приложений MFC
Мастер приложений MFC создает приложения, при компиляции реализует базовые возможности приложения Windows исполняемого файла (.exe). Начальное приложение MFC включает (.cpp) исходные файлы C++, файлы ресурсов (RC), файлы заголовков (h) и файл проекта (VCXPROJ). Код, созданный в этих начальных файлах основан на MFC.  
  
> [!NOTE]
>  В зависимости от выбранных параметров мастер создает дополнительные файлы в проекте. Например, при выборе **контекстной справки** на [дополнительные функции](../../mfc/reference/advanced-features-mfc-application-wizard.md) страницы, мастер создает файлы, необходимые для компиляции файлов справки проекта. Дополнительные сведения о файлах, создаваемых мастером см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md)и содержатся в файле Readme.txt в проекте.  
  
## <a name="overview"></a>Обзор  
 На этой странице мастера описываются текущие параметры приложения для создаваемого приложения MFC. По умолчанию мастер создает проект следующим образом:  
  
-   [Тип приложения, мастер приложений MFC](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   Создается проект с поддержкой с вкладками многодокументного интерфейса (MDI). Дополнительные сведения см. в разделе [SDI и MDI](../../mfc/sdi-and-mdi.md).  
  
    -   В проекте используется [архитектуры Document/View](../../mfc/document-view-architecture.md).  
  
    -   В проекте используются библиотеки Юникод.  
  
    -   Проект создается с помощью стиль проекта Visual Studio и включает смену визуального стиля.  
  
    -   Проект использует MFC в общей DLL. Дополнительные сведения см. в разделе [библиотеки DLL в Visual C++](../../build/dlls-in-visual-cpp.md).  
  
-   [Поддержка составных документов, мастер приложений MFC](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   Проект не поддерживает составных документов.  
  
-   [Страница "Строки шаблонов документов" мастера приложений MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   В проекте используется имя проекта для строки шаблонов документов по умолчанию.  
  
-   [Поддержка базы данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   Проект не поддерживает базы данных.  
  
-   [Параметры пользовательского интерфейса, мастер приложений MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   Проект реализует стандартный пользовательский интерфейс такие компоненты, как системное меню, строка состояния, кнопки свертывания диалоговые окна, и для Windows **о** поле, стандартные меню и закрепления панели инструментов и дочерних фреймов.  
  
-   [Страница "Дополнительные возможности" мастера приложений MFC](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   Проект поддерживает печать и предварительный просмотр.  
  
    -   Проект поддерживает элементы управления ActiveX. Дополнительные сведения см. в разделе [последовательность операций для создания элементов управления ActiveX](../../mfc/sequence-of-operations-for-creating-activex-controls.md).  
  
    -   Проект не поддерживает [автоматизации](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), или Active Accessibility.  
  
    -   Проект поддерживает **Explorer** закрепляемой области **вывод** закрепляемой области и **свойства** закрепления панели.  
  
-   [Создаваемые классы, мастер приложений MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   Класс представления проекта является производным от [CView Class](../../mfc/reference/cview-class.md).  
  
    -   Класс приложения проекта является производным от [CWinAppEx класс](../../mfc/reference/cwinappex-class.md).  
  
    -   Класс документа проекта является производным от [CDocument-класс](../../mfc/reference/cdocument-class.md).  
  
    -   Класс основного фрейма проекта является производным от [класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md).  
  
    -   Класс фрейма дочернего проекта является производным от [класс CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md).  
  
 Чтобы изменить эти параметры по умолчанию, щелкните соответствующую вкладку заголовок в левом столбце мастера и внесите изменения на появившейся странице.  
  
 После создания проекта приложения MFC можно добавить объекты и элементы управления в проект с помощью Visual C++ [мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md)   
 [Настольных приложений MFC](../../mfc/mfc-desktop-applications.md)   
 [Использование классов для создания приложений для Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
