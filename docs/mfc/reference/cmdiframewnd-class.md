---
title: Класс CMDIFrameWnd
ms.date: 11/04/2016
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
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: 9d9a2d33f61aa9033bb17c090989b4f08ee82bd7
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178386"
---
# <a name="cmdiframewnd-class"></a>Класс CMDIFrameWnd

Предоставляет функции фреймового окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Создает документ `CMDIFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDIFrameWnd::CreateClient](#createclient)|Создает окно Windows MDICLIENT для данного `CMDIFrameWnd`. Вызывается средой `OnCreate` функцию-член `CWnd`.|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Создает новое дочернее окно.|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Возвращает окно во всплывающем меню.|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Активирует различные дочернего окна интерфейса MDI.|
|[CMDIFrameWnd::MDICascade](#mdicascade)|Упорядочивает все дочерние окна в виде каскадными.|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Извлекает текущий активный дочернего окна MDI, а также флаг, указывающий ли дочерние находящегося в развернутом состоянии.|
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Упорядочивает все свернутые документа дочерние окна.|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Разворачивает дочернего окна MDI.|
|[CMDIFrameWnd::MDINext](#mdinext)|Активирует дочернее окно сразу за окном текущему активному дочернему и помещает в данный момент активное дочернее окно за все дочерние окна.|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Активирует предыдущего дочернего окна и располагает окно текущему активному дочернему сразу за ней.|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Восстанавливает дочернего окна MDI из развернутой или свернутой размер.|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Заменяет меню фрейма окна интерфейса MDI и окна во всплывающем меню.|
|[CMDIFrameWnd::MDITile](#mditile)|Упорядочивает все дочерние окна в виде мозаики.|

## <a name="remarks"></a>Примечания

Чтобы создать полезные окно области MDI для вашего приложения, являются производными от класса `CMDIFrameWnd`. Добавьте переменные-члены производного класса для хранения данных, к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Окно области MDI можно создать путем вызова [создать](../../mfc/reference/cframewnd-class.md#create) или [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) функцию-член `CFrameWnd`.

Перед вызовом метода `Create` или `LoadFrame`, то необходимо создать объект окна фрейма в куче, с помощью C++ **новый** оператор. Перед вызовом `Create` вы также можете зарегистрировать класс окна с [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальную функцию, чтобы задать значок и класс стили рамки.

Используйте `Create` функция-член для передачи в интерпретации аргументов параметры создания фрейма.

`LoadFrame` требуется меньшее количество аргументов, чем `Create`и вместо этого получает большинство его значений по умолчанию из ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню фрейма. Доступ к `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Хотя `MDIFrameWnd` является производным от `CFrameWnd`, производный от класса окна фрейма `CMDIFrameWnd` не должны быть объявлены с `DECLARE_DYNCREATE`.

`CMDIFrameWnd` Класс наследует большую часть реализацию по умолчанию от `CFrameWnd`. Подробный список этих функций см. в разделе [CFrameWnd](../../mfc/reference/cframewnd-class.md) Описание класса. `CMDIFrameWnd` Класс имеет следующие дополнительные возможности:

- Окно области MDI управляет mdiclient-окно, изменить его расположение в сочетании с панели элементов управления. Клиентское MDI окно имеет непосредственного родительского фрейма дочерних MDI-окон. Стили окна WS_HSCROLL и WS_VSCROLL, указанные на `CMDIFrameWnd` применяются к клиентское MDI окно вместо фрейма главного окна, поэтому пользователь может воспользоваться прокруткой клиентской области MDI (как в Windows руководитель программы, например).

- Окно области MDI является владельцем меню по умолчанию, которое используется в качестве строки меню, при наличии не активную дочернюю MDI. При отсутствии активной дочерней MDI-формы, строке меню Окно области MDI автоматически заменяется окно дочернего меню MDI.

- Окно области MDI работает совместно с текущего дочернего окна MDI, если таковой имеется. Например сообщения команды делегируются активной дочерней MDI-формы, прежде чем окно области MDI.

- Окно области MDI имеет обработчики по умолчанию для следующих стандартных команд меню окна:

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- Окно области MDI также содержит реализацию ID_WINDOW_NEW, который создает новый кадр и представления в текущем документе. Приложение может переопределить эти реализации команд по умолчанию для настройки обработки окна MDI.

Не используйте C++ **удалить** оператор для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow`. `CFrameWnd` Реализация `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно по умолчанию `OnClose` вызовет обработчик `DestroyWindow`.

Дополнительные сведения о `CMDIFrameWnd`, см. в разделе [фрейма Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd

Создает объект `CMDIFrameWnd`.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Примечания

Вызовите `Create` или `LoadFrame` функция-член для создания видимым окно области MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>  CMDIFrameWnd::CreateClient

Создает клиентское MDI окно, который управляет `CMDIChildWnd` объектов.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*lpCreateStruct*<br/>
Длинный указатель на [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) структуры.

*pWindowMenu*<br/>
Указатель на окно во всплывающем меню.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член должен вызываться при переопределении `OnCreate` непосредственно функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>  CMDIFrameWnd::CreateNewChild

Создает новое дочернее окно.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>Параметры

*pClass*<br/>
Класс времени выполнения дочернего окна должен быть создан.

*Ресурсов*<br/>
Идентификатор общие ресурсы, связанные с дочернего окна.

*hMenu*<br/>
Меню дочернего окна.

*hAccel*<br/>
Ускоритель, дочернее окно.

### <a name="remarks"></a>Примечания

Эта функция создавать дочерние окна фрейма окна интерфейса MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup

Вызов этой функции-члена для получения дескриптора текущего всплывающего меню с именем «Window» (всплывающее меню с элементами для управления окнами MDI).

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Параметры

*hMenuBar*<br/>
Текущее меню.

### <a name="return-value"></a>Возвращаемое значение

Окно всплывающего меню, если один существует; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Реализация по умолчанию выполняет поиск всплывающего меню, содержащее стандартные команды меню окна, такие как ID_WINDOW_NEW и ID_WINDOW_TILE_HORZ.

Переопределите эту функцию-член, если у вас есть меню окна, которое не использует идентификаторы команд стандартного меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate

Активирует различные дочернего окна интерфейса MDI.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Параметры

*pWndActivate*<br/>
Указывает дочернего окна MDI активацию.

### <a name="remarks"></a>Примечания

Эта функция-член отправляет [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) дочернее окно активируется и дочерние окна сообщения.

Это же сообщение, которое отправляется в случае, если пользователь изменяет фокус на дочерние окна интерфейса MDI с помощью мыши или клавиатуры.

> [!NOTE]
>  Независимо от окно области MDI активируется дочернего окна MDI. Когда кадр становится активным, дочернее окно, последний раз была активирована отправляется [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) сообщение для рисования кадре активного окна и заголовок окна, но он не получает другое сообщение WM_MDIACTIVATE.

### <a name="example"></a>Пример

См. в примере [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).

##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade

Упорядочивает все дочерние окна MDI в формате cascade.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Указывает флаг cascade. Можно указать только следующего флага: MDITILE_SKIPDISABLED, что предотвращает отключенные дочерние окна интерфейса MDI каскадом.

### <a name="remarks"></a>Примечания

Первая версия `MDICascade`, без параметров, размещает все дочерние окна интерфейса MDI, включая тех, которые отключены. Вторая версия при необходимости выполняет не отключена cascade дочерних окон интерфейса MDI, если указать MDITILE_SKIPDISABLED для *nType* параметра.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive

Извлекает текущий активную дочернюю MDI, а также флаг, указывающий, развернута ли дочернее окно.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Параметры

*pbMaximized*<br/>
Указатель на возвращаемое значение BOOL. Присвоено значение TRUE, при возвращении, если окно развернуто; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на активное дочернее окно MDI.

### <a name="example"></a>Пример

См. в примере [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdiiconarrange"></a>  CMDIFrameWnd::MDIIconArrange

Упорядочивает все свернутые документа дочерние окна.

```
void MDIIconArrange();
```

### <a name="remarks"></a>Примечания

Он не влияет на дочерние окна, которые не находятся в свернутом состоянии.

### <a name="example"></a>Пример

См. в примере [CMDIFrameWnd::MDICascade](#mdicascade).

##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize

Разворачивает указанное окно дочерние MDI.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно для развертывания.

### <a name="remarks"></a>Примечания

Если дочернее окно развернуто, Windows изменяет размер, чтобы сделать свою клиентскую область окна клиента. Windows помещает дочернее окно элемента управления меню в строке меню фрейма, поэтому пользователь может восстановить или закрытия дочернего окна. Он также добавляет заголовок дочернего окна к заголовку окна фрейма.

Если другой дочернего окна интерфейса MDI активируется в том случае, когда дочернее окно текущего активного MDI находящегося в развернутом состоянии, Windows восстанавливает текущему активному дочернему и повышает активированного дочернее окно.

### <a name="example"></a>Пример

См. в примере [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext

Активирует дочернее окно сразу за окном текущему активному дочернему и помещает в данный момент активное дочернее окно за все дочерние окна.

```
void MDINext();
```

### <a name="remarks"></a>Примечания

Если развернуто дочернее окно текущего активного MDI, функция-член восстанавливает текущему активному дочернему и увеличивает активированного дочерних.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev

Активирует предыдущего дочернего окна и располагает окно текущему активному дочернему сразу за ней.

```
void MDIPrev();
```

### <a name="remarks"></a>Примечания

Если развернуто дочернее окно текущего активного MDI, функция-член восстанавливает текущему активному дочернему и увеличивает активированного дочерних.

##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore

Восстанавливает дочернего окна MDI из развернутой или свернутой размер.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно для восстановления.

### <a name="example"></a>Пример

См. в примере [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu

Заменяет меню фрейма окна интерфейса MDI и окна во всплывающем меню.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*pFrameMenu*<br/>
Задает меню нового меню окна фрейма. Если значение равно NULL, меню не меняется.

*pWindowMenu*<br/>
Задает меню нового окна во всплывающем меню. Если значение равно NULL, меню не меняется.

### <a name="return-value"></a>Возвращаемое значение

Указатель на меню окна фрейма, заменены это сообщение. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Примечания

После вызова метода `MDISetMenu`, приложение должно вызвать [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) функцию-член `CWnd` обновление строки меню.

Если этот вызов заменяет всплывающего меню окна, пункты меню дочернего окна MDI удаляются из предыдущих меню "окно" и добавлен новый окна во всплывающем меню.

Если этот вызов приводит к замене меню окна фрейма MDI дочернего окна MDI находящегося в развернутом состоянии, в элементы управления элемента управления меню и восстановления удаляются из в предыдущем меню окна фрейма и добавить новое меню.

Не вызывайте эту функцию-член, если вы используете платформу для управления вашей дочерних окон интерфейса MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>  CMDIFrameWnd::MDITile

Упорядочивает все дочерние окна в виде мозаики.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Указывает флаг мозаичное заполнение. Этот параметр может принимать любое из следующих флагов:

- MDITILE_HORIZONTAL плитки дочерних окон интерфейса MDI, что одно окно отображается над другой.

- Предотвращает MDITILE_SKIPDISABLED отключенные дочерние окна MDI из выполняется мозаичное заполнение.

- MDITILE_VERTICAL плитки дочерних окон интерфейса MDI, что одно окно отображается рядом с другой.

### <a name="remarks"></a>Примечания

Первая версия `MDITile`, без параметров, плитки по вертикали в Windows 3.1 и более поздних версиях windows. Вторая версия плитки windows горизонтально или вертикально, в зависимости от значения *nType* параметра.

### <a name="example"></a>Пример

См. в примере [CMDIFrameWnd::MDICascade](#mdicascade).

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../visual-cpp-samples.md)<br/>
[Пример MFC MDIDOCVW](../../visual-cpp-samples.md)<br/>
[Пример MFC: SNAPVW](../../visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
