---
title: "CMDIFrameWnd-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 8ede1eef9812bb7aa5a1f127ac571f101c40dd29
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

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
|[CMDIFrameWnd::CreateClient](#createclient)|Создается Windows **MDICLIENT** окна для этого `CMDIFrameWnd`. Вызывается методом `OnCreate` функции-члена `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Создает новое дочернее окно.|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Возвращает окно во всплывающем меню.|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Активирует другого дочернего окна MDI.|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|Упорядочивает все дочерние окна каскадом формат.|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Извлекает текущий активный дочернего окна MDI, а также флаг, указывающий, ли дочерние развернуто.|  
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Упорядочивает все свернутые документа дочерние окна.|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Развертывает дочернего окна MDI.|  
|[CMDIFrameWnd::MDINext](#mdinext)|Активирует дочернее окно сразу же за текущей активной дочернее окно и помещает в данный момент активное дочернее окно за все дочерние окна.|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Активирует предыдущих дочернее окно и помещает активного дочернего окна непосредственно под ним.|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Восстанавливает дочернего окна MDI из развернутого или свернутого размер.|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Заменяет окне фрейма MDI в меню и окна во всплывающем меню.|  
|[CMDIFrameWnd::MDITile](#mditile)|Упорядочивает все дочерние окна в формате мозаики.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать полезные окно области MDI для приложения, создайте класс, производный от `CMDIFrameWnd`. Добавьте переменные-члены в производный класс для хранения данных, относящихся к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Окно области MDI можно создать путем вызова [создать](../../mfc/reference/cframewnd-class.md#create) или [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) функции-члена `CFrameWnd`.  
  
 Перед вызовом метода **создать** или `LoadFrame`, следует создать объект окна фрейма в куче, с помощью C++ **новый** оператор. Перед вызовом метода **создать** можно также зарегистрировать класс окна с [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции, чтобы задать значок и класс стили рамки.  
  
 Используйте **создать** функции-члена для передачи как интерпретации аргументов параметры создания фрейма.  
  
 `LoadFrame`требуется меньшее количество аргументов, чем **создать**и вместо этого извлекает большую часть значений по умолчанию из ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню опорного кадра. Доступ к `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, **IDR_MAINFRAME**).  
  
 Хотя **MDIFrameWnd** является производным от `CFrameWnd`, класс окна фрейма, производный от `CMDIFrameWnd` не требуется объявлять с `DECLARE_DYNCREATE`.  
  
 `CMDIFrameWnd` Класс наследует большую часть его реализация по умолчанию из `CFrameWnd`. Подробный список этих функций см. в разделе [CFrameWnd](../../mfc/reference/cframewnd-class.md) Описание класса. `CMDIFrameWnd` Класс имеет следующие дополнительные возможности:  
  
-   Управляет окне фрейма MDI **MDICLIENT** окна, изменения положения его вместе с панели элементов управления. Клиентское MDI окно является непосредственным родительским кадра дочерние MDI-окна. **WS_HSCROLL** и **WS_VSCROLL** окна стили, заданные на `CMDIFrameWnd` применяются к клиентское MDI окно вместо фрейма главного окна, поэтому пользователь может воспользоваться прокруткой клиентской области MDI (как программы Диспетчер Windows, например).  
  
-   Окно области MDI владеет меню по умолчанию, которое используется в качестве строки меню, при наличии не активную дочернюю MDI. При наличии активной дочерней формы MDI, окно области MDI меню автоматически заменяется окно дочернего меню MDI.  
  
-   Окно области MDI работает совместно с текущее дочернее окно MDI-приложения, если таковой имеется. Для экземпляра сообщения команд, делегируются в текущей активной дочерней MDI-формы перед окно области MDI.  
  
-   Окно области MDI содержит обработчики событий по умолчанию для следующих стандартных команд меню окна:  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   Окно области MDI, также содержит реализацию **ID_WINDOW_NEW**, которая создает новый фрейм и представление в текущем документе. Приложение может переопределить эти реализации по умолчанию команды для настройки обработки окна MDI.  
  
 Не используйте C++ **удалить** оператор для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow` . `CFrameWnd` Реализация `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно фрейма, значение по умолчанию `OnClose` обработчик вызовет `DestroyWindow`.  
  
 Дополнительные сведения о `CMDIFrameWnd`, в разделе [фреймов](../../mfc/frame-windows.md).  
  
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
 Вызовите **создать** или `LoadFrame` функции-члена для создания отображается окно области MDI.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="createclient"></a>CMDIFrameWnd::CreateClient  
 Создает клиентское MDI окно, который управляет `CMDIChildWnd` объектов.  
  
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
 Эта функция-член должен вызываться при переопределении `OnCreate` непосредственно функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild  
 Создает новое дочернее окно.  
  
```  
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,  
    UINT nResource,  
    HMENU hMenu = NULL,  
    HACCEL hAccel = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pClass`  
 Класс среды выполнения дочернего окна должен быть создан.  
  
 *nResource*  
 Идентификатор общие ресурсы, связанные с дочернего окна.  
  
 `hMenu`  
 Меню дочернего окна.  
  
 `hAccel`  
 Дочернее окно сочетаний клавиш.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создавать дочерние окна MDI рамки окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 В этом примере показан фрагмент кода из статьи базы знаний Q201045, «Практическое руководство: добавлять несколько типов окна MDI Non-документ/представление приложения.» Статьи базы знаний можно найти по адресу [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup  
 Вызовите эту функцию-член для получения дескриптора текущего всплывающего меню «Окно» (всплывающее меню с элементами для управления окном MDI) с именем.  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>Параметры  
 *hMenuBar*  
 В текущем меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окно всплывающего меню, если один существует; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию ищет всплывающего меню, например, содержащий стандартные команды меню "окно" **ID_WINDOW_NEW** и **ID_WINDOW_TILE_HORZ**.  
  
 Переопределите эту функцию-член, если у вас есть меню окна, которые не используют идентификаторы команд меню «Стандартная».  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing № 16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate  
 Активирует другого дочернего окна MDI.  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndActivate*  
 Указывает дочернего окна MDI, необходимо активировать.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член отправляет [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) сообщений дочернего окна активации и дочернее окно быть активным.  
  
 Это же сообщение отправляется при перемещении пользователем фокуса на дочернего окна MDI с помощью мыши или клавиатуры.  
  
> [!NOTE]
>  Независимо от окно области MDI активации дочернего окна MDI. Когда кадр становится активным, дочернее окно, последний раз была активирована отправляется [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) сообщений для отрисовки активного окна фрейма и строки заголовка, но не принимаются `WM_MDIACTIVATE` сообщения.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).  
  
##  <a name="mdicascade"></a>CMDIFrameWnd::MDICascade  
 Упорядочивает все дочерние окна MDI в формате cascade.  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>Параметры  
 `nType`  
 Задает флаг cascade. Можно указать только следующий флаг: `MDITILE_SKIPDISABLED`, что предотвращает каскадно отключенные дочерние окна MDI.  
  
### <a name="remarks"></a>Примечания  
 В первой версии `MDICascade`, без параметров каскадным образом распространяется всех дочерних MDI-окон, включая отключена из них. Вторая версия (необязательно) не отключена cascade дочерних MDI-окон Если не указать `MDITILE_SKIPDISABLED` для `nType` параметра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing 17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive  
 Извлекает текущий активную дочернюю MDI, а также флаг, указывающий, развернута ли дочернего окна.  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pbMaximized*  
 Указатель на **BOOL** возвращаемое значение. Значение **TRUE** при возвращении, если это окно находится в развернутом состоянии; в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активное дочернее окно MDI.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconArrange  
 Упорядочивает все свернутые документа дочерние окна.  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>Примечания  
 Он не влияет на дочерние окна, которые не сворачиваются.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMDIFrameWnd::MDICascade](#mdicascade).  
  
##  <a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize  
 Развертывает указанного дочернего окна MDI.  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, чтобы максимально увеличить.  
  
### <a name="remarks"></a>Примечания  
 Когда оно развернуто дочернее окно Windows изменяет его, чтобы изменения клиентской области заполнения в окне клиента. Windows помещает дочернего окна элемента управления меню в строке меню фрейма, пользователь имеет возможность восстановления и закрытия дочернего окна. Он также добавляет заголовок дочернего окна с заголовком окна фрейма.  
  
 Если другой дочернее окно MDI активируется, когда оно развернуто дочернее окно текущего активного интерфейса MDI, Windows восстанавливает текущей активной дочерней и повышает вновь активированные дочернего окна.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdinext"></a>CMDIFrameWnd::MDINext  
 Активирует дочернее окно сразу же за текущей активной дочернее окно и помещает в данный момент активное дочернее окно за все дочерние окна.  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>Примечания  
 Если развернуто дочернее окно текущего активного интерфейса MDI, функция-член восстанавливает текущей активной дочерней и повышает вновь активированные дочерних.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing 18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>CMDIFrameWnd::MDIPrev  
 Активирует предыдущих дочернее окно и помещает активного дочернего окна непосредственно под ним.  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>Примечания  
 Если развернуто дочернее окно текущего активного интерфейса MDI, функция-член восстанавливает текущей активной дочерней и повышает вновь активированные дочерних.  
  
##  <a name="mdirestore"></a>CMDIFrameWnd::MDIRestore  
 Восстанавливает дочернего окна MDI из развернутого или свернутого размер.  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает для окна, чтобы восстановить.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).  
  
##  <a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu  
 Заменяет окне фрейма MDI в меню и окна во всплывающем меню.  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Параметры  
 *pFrameMenu*  
 Задает меню новое меню окна фрейма. Если **NULL**, меню не меняется.  
  
 `pWindowMenu`  
 Задает меню нового окна во всплывающем меню. Если **NULL**, меню не меняется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на меню окна фрейма, заменяется это сообщение. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `MDISetMenu`, приложение должно вызвать [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) функции-члена `CWnd` для обновления строки меню.  
  
 Если этот вызов заменяет всплывающего меню окна, элементы меню дочернего окна MDI удаляются из предыдущих меню окна и добавлены новые окна во всплывающем меню.  
  
 Если развернуто дочернего окна MDI и этот вызов заменяет меню окна фрейма MDI, элементы управления меню и восстановления удаляются из предыдущих меню окна фрейма и добавлено новое меню.  
  
 Не вызывайте эту функцию-член, если использовать платформу для управления вашей дочерние окна MDI.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing 19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing № 20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>CMDIFrameWnd::MDITile  
 Упорядочивает все дочерние окна в формате мозаики.  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>Параметры  
 `nType`  
 Задает флаг мозаичное заполнение. Этот параметр может иметь одно из следующих флагов:  
  
- `MDITILE_HORIZONTAL`Плитки дочерних MDI-окон, что одно окно появляется над другой.  
  
- `MDITILE_SKIPDISABLED`Запрещает выполняется мозаичное заполнение отключенные дочерние окна MDI.  
  
- `MDITILE_VERTICAL`Плитки дочерних MDI-окон, что одно окно появится рядом с другом.  
  
### <a name="remarks"></a>Примечания  
 В первой версии `MDITile`, без параметров, размещает окна по вертикали в группе Windows версии 3.1 и более поздней версии. Вторая версия плитки windows горизонтально или вертикально, в зависимости от значения `nType` параметра.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMDIFrameWnd::MDICascade](#mdicascade).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Пример MFC MDIDOCVW](../../visual-cpp-samples.md)   
 [Пример MFC: SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)

