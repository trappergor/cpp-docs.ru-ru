---
title: "CMDIFrameWnd-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
dev_langs:
- C++
helpviewer_keywords:
- MDI frame windows
- CMDIFrameWnd class
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0eae6c14038dd27a5779757d1807068fbe865b81
ms.lasthandoff: 02/24/2017

---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd-класс
Предоставляет функции фреймового окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Создает документ `CMDIFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](#createclient)|Windows создает **MDICLIENT** окно для этого `CMDIFrameWnd`. Вызывается методом `OnCreate` функции-члена `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Создание нового дочернего окна.|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Возвращает окно во всплывающем меню.|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Активирует различных дочернего окна MDI.|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|Упорядочивает все дочерние окна каскадом формат.|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Получает активный дочернего окна MDI, а также флаг, указывающий, ли дочерние развернуто.|  
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Располагает все свернутые документа дочерние окна.|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Разворачивает дочернего окна MDI.|  
|[CMDIFrameWnd::MDINext](#mdinext)|Активирует дочернее окно сразу же за текущей активной дочернего окна и помещает активного дочернее окно за все дочерние окна.|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Активирует предыдущего дочернего окна и помещает активной дочернего окна сразу под ним.|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Восстанавливает дочернего окна MDI из развернутой или свернутой размер.|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Заменяет в окне фрейма MDI меню и контекстного меню окна.|  
|[CMDIFrameWnd::MDITile](#mditile)|Упорядочивает все дочерние окна в виде мозаики.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать полезные окно области MDI в приложении, создайте класс, производный от `CMDIFrameWnd`. Добавьте переменные-члены для производного класса для хранения данных, относящихся к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Окно области MDI можно создать путем вызова [создать](../../mfc/reference/cframewnd-class.md#create) или [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) функции-члена `CFrameWnd`.  
  
 Перед вызовом метода **создать** или `LoadFrame`, необходимо создать объект окна фрейма в куче C++ с помощью **новый** оператор. Перед вызовом метода **создать** можно также зарегистрировать класс окна с [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальные функции для установки значок и класс стили рамки.  
  
 Используйте **создать** для передачи параметров создания фрейма как интерпретации аргументов функции-члена.  
  
 `LoadFrame`требуется меньшее число аргументов, чем **создать**и вместо этого получает большую часть значений по умолчанию из ресурсов, включая заголовок, значок, таблицы сочетаний клавиш и меню фрейма. Доступ к `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, **IDR_MAINFRAME**).  
  
 Хотя **MDIFrameWnd** является производным от `CFrameWnd`, производный класс фреймового окна из `CMDIFrameWnd` не требуется объявлять с `DECLARE_DYNCREATE`.  
  
 `CMDIFrameWnd` Класс наследует большую часть реализацию по умолчанию от `CFrameWnd`. Подробный список этих функций см. [CFrameWnd](../../mfc/reference/cframewnd-class.md) Описание класса. `CMDIFrameWnd` Класс имеет следующие дополнительные возможности:  
  
-   Окно области MDI управляет **MDICLIENT** окна, изменения положения его в сочетании с панели элементов управления. В окне клиента MDI является прямым родителем кадров дочерних MDI-окон. **WS_HSCROLL** и **WS_VSCROLL** окно стили, заданные на `CMDIFrameWnd` применяются к окну MDI клиента вместо фрейма главного окна, поэтому пользователь может воспользоваться прокруткой клиентской области MDI (как в программе Диспетчер Windows, например).  
  
-   Окно области MDI владеет меню по умолчанию, который используется в качестве меню, если нет активных дочернего окна MDI. При наличии активной дочерней MDI-формы, окно области MDI меню автоматически заменяется окно дочернего меню MDI.  
  
-   Окно области MDI работает совместно с текущего дочернего окна MDI, если таковой имеется. Например сообщения команд делегируются активной дочерней MDI-формы, прежде чем окно области MDI.  
  
-   Окно области MDI содержит обработчики событий по умолчанию для следующих стандартных команд меню окна:  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   Окно области MDI также содержит реализацию **ID_WINDOW_NEW**, и создается новый кадр и представление в текущем документе. Приложение может переопределить эти реализации команд по умолчанию для настройки обработки окна MDI.  
  
 Не используйте C++ **удаление** оператор уничтожении окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow` . `CFrameWnd` Реализацию `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно области по умолчанию `OnClose` обработчик вызовет `DestroyWindow`.  
  
 Дополнительные сведения о `CMDIFrameWnd`, в разделе [окна фрейма](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd  
 Создает объект `CMDIFrameWnd`.  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов **создать** или `LoadFrame` функции-члена для создания видимым окно области MDI.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#13;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="createclient"></a>CMDIFrameWnd::CreateClient  
 Создает окно MDI-приложения клиента, которое управляет `CMDIChildWnd` объектов.  
  
```  
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Параметры  
 `lpCreateStruct`  
 Длинный указатель [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) структуры.  
  
 `pWindowMenu`  
 Указатель на окно во всплывающем меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член должен вызываться при переопределении `OnCreate` напрямую функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#14;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild  
 Создание нового дочернего окна.  
  
```  
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,  
    UINT nResource,  
    HMENU hMenu = NULL,  
    HACCEL hAccel = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pClass`  
 Класс дочернего окна должен быть создан во время выполнения.  
  
 *nResource*  
 Идентификатор общие ресурсы, связанные с дочернего окна.  
  
 `hMenu`  
 Меню дочернего окна.  
  
 `hAccel`  
 Ускоритель дочернего окна.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для создания дочерних окон MDI-окно фрейма.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#15;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 Данный пример является выдержкой из статьи базы знаний Q201045, «Практическое руководство: добавлять несколько типов окна MDI без документов и представлений приложение.» Статьи базы знаний, доступны в документации по Visual Studio библиотеки MSDN или в [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup  
 Вызовите эту функцию-член для получения дескриптора для текущего контекстного меню с именем «Окно» (всплывающее меню с элементами для управления окном MDI).  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>Параметры  
 *hMenuBar*  
 Текущее меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окно всплывающего меню, если он существует; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию ищет всплывающего меню, содержащий стандартные команды меню окна, такие как **ID_WINDOW_NEW** и **ID_WINDOW_TILE_HORZ**.  
  
 При наличии меню окна, которые не используют идентификаторы команд стандартного меню, переопределяют эту функцию-член.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing №&16;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate  
 Активирует различных дочернего окна MDI.  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndActivate*  
 Указывает для дочернего окна MDI активации.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член отправляет [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) дочернего окна активации и отключения дочернее окно сообщения.  
  
 Это же сообщение, которое отправляется, если пользователь изменяет фокус на дочернем окне MDI с помощью мыши или клавиатуры.  
  
> [!NOTE]
>  Независимо от окно области MDI активируется дочернего окна MDI. Когда кадр становится активным, дочернее окно, последний раз была активирована отправляется [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) сообщений для отрисовки активного окна и строки заголовка, но не принимаются `WM_MDIACTIVATE` сообщение.  
  
### <a name="example"></a>Пример  
 В примере показано [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).  
  
##  <a name="mdicascade"></a>CMDIFrameWnd::MDICascade  
 Упорядочивает все дочерние окна MDI в формате cascade.  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>Параметры  
 `nType`  
 Задает флаг cascade. Можно указать только следующий флаг: `MDITILE_SKIPDISABLED`, запрещающая отключенных дочерних MDI-окон каскадом.  
  
### <a name="remarks"></a>Примечания  
 Первая версия `MDICascade`, без параметров распространяется на все дочерние окна MDI, включая отключена из них. Второй версии, при необходимости не не отключена cascade дочерних MDI-окон, при указании `MDITILE_SKIPDISABLED` для `nType` параметр.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&17;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive  
 Получает текущий активную дочернюю MDI, а также флаг, указывающий, развернута ли дочернего окна.  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pbMaximized*  
 Указатель на **BOOL** возвращаемое значение. Значение **TRUE** при возвращении, если окно в развернутом состоянии; в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активную дочернюю MDI.  
  
### <a name="example"></a>Пример  
 В примере показано [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconArrange  
 Располагает все свернутые документа дочерние окна.  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>Примечания  
 Он не влияет на дочерние окна, которые не сворачиваются.  
  
### <a name="example"></a>Пример  
 В примере показано [CMDIFrameWnd::MDICascade](#mdicascade).  
  
##  <a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize  
 Разворачивает указанного дочернего окна MDI.  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает для окна, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Если дочернее окно развернуто, Windows изменяет его, чтобы сделать свою клиентскую область заливки в окне клиента. Windows помещает дочернего окна элемента управления меню в строке меню фрейма, пользователь имеет возможность восстановления и закрытия дочернего окна. Он также добавляет заголовок дочернего окна с заголовком окна фрейма.  
  
 Если другого дочернего окна MDI активируется, когда оно развернуто дочернее окно текущего активного MDI, Windows восстанавливает текущей активной дочерней и увеличивает вновь активированные дочернего окна.  
  
### <a name="example"></a>Пример  
 В примере показано [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdinext"></a>CMDIFrameWnd::MDINext  
 Активирует дочернее окно сразу же за текущей активной дочернего окна и помещает активного дочернее окно за все дочерние окна.  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>Примечания  
 Если развернуто дочернее окно текущего активного MDI, функция-член восстанавливает текущей активной дочерней и увеличивает вновь активированные дочерних.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&18;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>CMDIFrameWnd::MDIPrev  
 Активирует предыдущего дочернего окна и помещает активной дочернего окна сразу под ним.  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>Примечания  
 Если развернуто дочернее окно текущего активного MDI, функция-член восстанавливает текущей активной дочерней и увеличивает вновь активированные дочерних.  
  
##  <a name="mdirestore"></a>CMDIFrameWnd::MDIRestore  
 Восстанавливает дочернего окна MDI из развернутой или свернутой размер.  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает для окна, чтобы восстановить.  
  
### <a name="example"></a>Пример  
 В примере показано [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).  
  
##  <a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu  
 Заменяет в окне фрейма MDI меню и контекстного меню окна.  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Параметры  
 *pFrameMenu*  
 Задает меню новое меню окна фрейма. Если **NULL**, меню не изменяется.  
  
 `pWindowMenu`  
 Задает меню нового окна контекстного меню. Если **NULL**, меню не изменяется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на меню окна фрейма, заменяется это сообщение. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `MDISetMenu`, приложение должно вызвать [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) функции-члена `CWnd` для обновления строки меню.  
  
 Если этот вызов заменяет контекстного меню окна, элементы меню дочернего окна MDI удаляются из предыдущего меню окна и добавить новые окна контекстного меню.  
  
 Если развернуто дочернего окна MDI и заменяет этот вызов меню окна фрейма MDI, элементы управления меню и восстановления удаляются из предыдущих меню окна фрейма и добавить новое меню.  
  
 Не следует вызывать эту функцию-член, если использовать платформу для управления дочерних окон MDI.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&19;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&20;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>CMDIFrameWnd::MDITile  
 Упорядочивает все дочерние окна в виде мозаики.  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>Параметры  
 `nType`  
 Задает флаг мозаичное заполнение. Этот параметр может иметь одно из следующих флагов:  
  
- `MDITILE_HORIZONTAL`Плитки дочерних MDI-окон, что одно окно отображается над другой.  
  
- `MDITILE_SKIPDISABLED`Запрещает выполняется мозаичное заполнение отключенные дочерние окна MDI.  
  
- `MDITILE_VERTICAL`Плитки дочерних MDI-окон, что одно окно появится рядом с другом.  
  
### <a name="remarks"></a>Примечания  
 Первая версия `MDITile`, без параметров, располагает окна по вертикали в Windows версии 3.1 и более поздней версии. Вторая версия плитки windows горизонтально или вертикально, в зависимости от значения `nType` параметр.  
  
### <a name="example"></a>Пример  
 В примере показано [CMDIFrameWnd::MDICascade](#mdicascade).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [MFC примера MDIDOCVW](../../visual-cpp-samples.md)   
 [Пример MFC SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd-класс](../../mfc/reference/cmdichildwnd-class.md)

