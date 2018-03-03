---
title: "Программа MFC или системы управления версиями и файлы заголовков | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adb4ba4fdcc141438b2eeb87b4e3c9151bb9a5c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-program-or-control-source-and-header-files"></a>Программа MFC или управление файлами исходного кода и заголовков
Следующие файлы создаются при создании проекта MFC в Visual Studio, в зависимости от параметров, выбранных для создаваемого проекта. Например, проект содержит *Projname*dlg.cpp и *Projname*dlg.h файлы только в том случае, если вы создаете проект на базе диалогового окна или класса.  
  
 Все эти файлы расположены в *Projname* каталог и в папке файлов заголовков (h-файлы) или в папку исходных файлов (CPP-файлы) в обозревателе решений.  
  
|Имя файла|Описание:|  
|---------------|-----------------|  
|*ProjName*.h|Главный файл заголовка для программы или библиотеки DLL. Он содержит все глобальные символы и `#include` директивы для других файлов заголовков. Он является производным `CPrjnameApp` класса из `CWinApp` и объявляет `InitInstance` функции-члена. Для элемента управления `CPrjnameApp` класс является производным от `COleControlModule`.|  
|*ProjName*.cpp|Исходный файл основной программы. Он создает один объект класса `CPrjnameApp`, который является производным от `CWinApp`и переопределяет `InitInstance` функции-члена.<br /><br /> Для исполняемых файлов `CPrjnameApp::InitInstance` выполняет ряд задач. Он регистрирует шаблоны документов, которые служат в качестве соединения между документами и представлениями; Создает окно главного фрейма; и создает пустой документ (или открывает документ, если он указан как аргумент командной строки для приложения).<br /><br /> Для элементов управления ActiveX (ранее OLE) и библиотеки DLL, `CProjNameApp::InitInstance` регистрирует фабрику объектов для элемента управления OLE, вызвав `COleObjectFactory::RegisterAll` и вызывает метод `AfxOLEInit`. Кроме того, функция-член `CProjNameApp::ExitInstance` используется выгрузить из памяти посредством вызова элемента управления **AfxOleTerm**.<br /><br /> Этот файл также регистрирует и отменяет регистрацию управления в базе данных регистрации Windows путем реализации `DllRegisterServer` и `DllUnregisterServer` функции.|  
|*ProjName*ctrl.h, *Projname*ctrl.cpp|Объявите и реализуйте `CProjnameCtrl` класса. `CProjnameCtrl`является производным от `COleControl`, и определенные общую схему реализации некоторых функций-членов, инициализации, рисования и сериализации (загрузки и сохранения) элемента управления. Сообщение, событий и схемы подготовки к отправке также определены.|  
|*ProjName*dlg.cpp, *Projname*dlg.h|Создан при выборе приложения на базе диалогового окна. Файлы наследования и реализации класса диалогового окна, с именем `CProjnameDlg`и включают функции-члены каркас для инициализации диалогового окна и выполнить обмен данными (диалоговых окон DDX). О классов диалоговых окон помещается в этих файлах, а не в *Projname*.cpp.|  
|Dlgproxy.cpp Dlgproxy.h|В основе диалоговых окон программы, реализации и заголовок файл для прокси-класса автоматизации проекта для главного диалогового окна. Используется, только если вы выбрали Поддержка модели автоматизации.|  
|*ProjName*doc.cpp, *Projname*doc.h|Наследования и реализации в классе документа с именем `CProjnameDoc`и включают функции-члены каркас для инициализации документа, сериализации (сохранения и загрузки) документа и реализации отладочной диагностики.|  
|*ProjName*set.h/.cpp|Создается, если создается программа, которая поддерживает базу данных и содержит класс набора записей.|  
|*ProjName*view.cpp, *Projname*view.h|Наследования и реализации класса представления, с именем `CProjnameView`, который используется для отображения и печати данных документа. `CProjnameView` Класс является производным от одного из следующих классов MFC:<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> Класс представления проекта содержит функции-члены каркас для рисования представления и реализации отладочной диагностики. Если включена поддержка печати, записи схемы сообщений добавляются для настройки печати, распечатать и печатать сообщения команд предварительного просмотра. Эти записи вызывают соответствующие функции-члены в базовом классе представления.|  
|*ProjName*PropPage.h, *Projname*PropPage.cpp|Объявите и реализуйте `CProjnamePropPage` класса. `CProjnamePropPage`является производным от `COlePropertyPage` и функцией-членом каркас, `DoDataExchange`, предоставляется для реализации обмена данными и проверки.|  
|IPframe.cpp IPframe.h|Если мини-сервера или полный сервер выбрано в мастере приложения создан **возможности автоматизации** (шаг 3 из 6). Файлы определяют и реализуют класс окна фрейма на месте, с именем **CInPlaceFrame**, используемый, когда сервер находится на месте активируется программой контейнера.|  
|MainFrm.cpp Mainfrm.h|Производные **CMainFrame** класса либо из [CFrameWnd](../mfc/reference/cframewnd-class.md) (для SDI-приложения) или [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (для приложений MDI). **CMainFrame** класс обрабатывает создание кнопок панели инструментов и строки состояния, если выбраны соответствующие параметры в мастере приложений **параметры приложения** (шаг 4 из 6). Дополнительные сведения об использовании **CMainFrame**, в разделе [фреймового окна созданы классы с помощью мастера приложений](../mfc/frame-window-classes-created-by-the-application-wizard.md).|  
|Childfrm.cpp Childfrm.h|Производные **CChildFrame** класса из [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md). **CChildFrame** класс используется для окна фрейма документа MDI. Эти файлы всегда создаются, если выбран параметр MDI.|  
  
## <a name="see-also"></a>См. также  
 [Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Программа ATL или управление исходного кода и файлы заголовков](../ide/atl-program-or-control-source-and-header-files.md)   
 [Проекты CLR](../ide/files-created-for-clr-projects.md)