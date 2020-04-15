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
ms.openlocfilehash: a6e68f6368a7b45e0a566a7d2d12f23a9cd62b12
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370059"
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
|[CMDIFrameWnd::CreateClient](#createclient)|Создает окно Windows MDICLIENT `CMDIFrameWnd`для этого. Вызывается `OnCreate` функцией `CWnd`члена .|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Создает новое окно ребенка.|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Возвращает всплывающее меню Window.|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Активирует другое окно ребенка MDI.|
|[CMDIFrameWnd::MDICascade](#mdicascade)|Упорядочив все детские окна в каскадном формате.|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Извлекает действующее в настоящее время окно дочернего MDI, а также флаг, указывающий, максимизируется ли у ребенка.|
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Упорядочив все минимизированные окна ребенка документа.|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Максимизирует окно ребенка MDI.|
|[CMDIFrameWnd::MDINext](#mdinext)|Активирует окно ребенка непосредственно за действующим в настоящее время окном ребенка и помещает в настоящее время активное окно ребенка за всеми другими окнами ребенка.|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Активирует предыдущее окно ребенка и помещает действующее в настоящее время окно ребенка непосредственно за ним.|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Восстанавливает окно ребенка MDI от максимального или минимизированного размера.|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Заменяет меню окна кадра MDI, всплывающее меню Window или и то, и другое.|
|[CMDIFrameWnd::MDITile](#mditile)|Упорядочив все детские окна в кафельном формате.|

## <a name="remarks"></a>Remarks

Чтобы создать полезное окно mDI кадра для `CMDIFrameWnd`вашего приложения, выберите класс из . Добавление переменных членов в полученный класс для хранения данных, специфичные для приложения. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Вы можете построить окно кадра MDI, позвонив в функцию `CFrameWnd`члена [Create](../../mfc/reference/cframewnd-class.md#create) или [LoadFrame.](../../mfc/reference/cframewnd-class.md#loadframe)

Перед `Create` вызовом `LoadFrame`или с помощью нового оператора с помощью **нового** оператора c-e необходимо построить объект окна рамы на куче. Перед `Create` вызовом вы также можете зарегистрировать класс окон с глобальной функцией [AfxRegisterWndClass,](application-information-and-management.md#afxregisterwndclass) чтобы установить значок и стили класса для кадра.

Используйте `Create` функцию члена, чтобы передать параметры создания кадра в качестве непосредственных аргументов.

`LoadFrame`требует меньше аргументов, чем, `Create`и вместо этого извлекает большую часть значений по умолчанию из ресурсов, включая подпись кадра, значок, таблицу акселератора и меню. Для доступа к `LoadFrame`ним все эти ресурсы должны иметь один и тот же идентификатор ресурсов (например, IDR_MAINFRAME).

Хотя `MDIFrameWnd` является производным от, `CFrameWnd`класс `CMDIFrameWnd` окна кадра, полученных из необходимости не быть объявлены с `DECLARE_DYNCREATE`.

Класс `CMDIFrameWnd` наследует большую часть `CFrameWnd`своей реализации по умолчанию от . Для получения подробного списка этих функций обратитесь к описанию класса [CFrameWnd.](../../mfc/reference/cframewnd-class.md) Класс `CMDIFrameWnd` имеет следующие дополнительные функции:

- Окно рамы MDI управляет окном MDICLIENT, переставая его в сочетании с барами управления. Окно клиента MDI является прямым родителем окон детской рамки MDI. WS_HSCROLL и WS_VSCROLL стили `CMDIFrameWnd` окнов, указанные в окне клиента MDI, а не к окну основной рамы, чтобы пользователь мог прокрутить область клиента MDI (например, в менеджере программы Windows).

- Окно кадра MDI имеет меню по умолчанию, которое используется в качестве панели меню, когда нет активного окна ребенка MDI. При наличии активного ребенка MDI панель меню окна mDI автоматически заменяется меню детского окна MDI.

- Окно кадра MDI работает в сочетании с текущим окном ребенка MDI, если он имеется. Например, командные сообщения делегируются действующему в настоящее время ребенку MDI перед окном кадра MDI.

- Окно кадра MDI имеет обработчики по умолчанию для следующих стандартных команд меню window:

  - ID_WINDOW_TILE_VERT

  - ID_WINDOW_TILE_HORZ

  - ID_WINDOW_CASCADE

  - ID_WINDOW_ARRANGE

- Окно кадра MDI также имеет реализацию ID_WINDOW_NEW, которая создает новую рамку и представление о текущем документе. Приложение может переопределить эти реализации команд по умолчанию для настройки обработки окон MDI.

Не используйте оператора **удаления** C's для уничтожения окна рамы. Используйте вместо этого `CWnd::DestroyWindow`. Реализация `CFrameWnd` `PostNcDestroy` будет удалять объект C's при уничтожении окна. Когда пользователь закрывает окно кадра, `OnClose` обработчик по умолчанию вызовет. `DestroyWindow`

Для получения `CMDIFrameWnd`дополнительной информации о, см. [Frame Windows](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd

Формирует объект `CMDIFrameWnd`.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Remarks

Вызов `Create` функции или `LoadFrame` функции участника для создания видимого окна кадра MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

## <a name="cmdiframewndcreateclient"></a><a name="createclient"></a>CMDIFrameWnd::CreateClient

Создает окно клиента MDI, `CMDIChildWnd` управляющее объектами.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*lpСоздатьСтрукт*<br/>
Длинный указатель на структуру [CREATESTRUCT.](/windows/win32/api/winuser/ns-winuser-createstructw)

*pWindowMenu*<br/>
Указатель на всплывающее меню Window.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена должна быть вызвана, если вы переопределяете функцию `OnCreate` участника напрямую.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

## <a name="cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild

Создает новое окно ребенка.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>Параметры

*pClass*<br/>
Класс времени выполнения создаваемого окна ребенка.

*nРесурс*<br/>
Идентификатор общих ресурсов, связанных с окном ребенка.

*hMenu*<br/>
Меню окна ребенка.

*hAccel*<br/>
Ускоритель детского окна.

### <a name="remarks"></a>Remarks

Используйте эту функцию для создания детских окон окна кадровmMM.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

## <a name="cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup

Позвоните в эту функцию участника, чтобы получить ручку текущего всплывающее меню под названием "Окно" (всплывающее меню с элементами меню для управления окнами MDI).

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Параметры

*hMenuBar*<br/>
Текущий бар меню.

### <a name="return-value"></a>Возвращаемое значение

Всплывающее меню Окна, если он существует; в противном случае NULL.

### <a name="remarks"></a>Remarks

Реализация по умолчанию ищет всплывающее меню, содержащее стандартные команды меню Window, такие как ID_WINDOW_NEW и ID_WINDOW_TILE_HORZ.

Переопределить эту функцию участника, если у вас есть меню Window, в которое не используются стандартные иди команд меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

## <a name="cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate

Активирует другое окно ребенка MDI.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Параметры

*pWndActivate*<br/>
Указывает на окно ребенка MDI для активации.

### <a name="remarks"></a>Remarks

Эта функция члена отправляет [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) сообщение как в активированное окно ребенка, так и в деактивацию окна ребенка.

Это то же самое сообщение, которое отправляется, если пользователь меняет фокус на окне ребенка MDI с помощью мыши или клавиатуры.

> [!NOTE]
> Окно ребенка MDI активируется независимо от окна рамы MDI. Когда кадр становится активным, в последнее время в окне ребенка, активированного, отправляется [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) сообщение для рисования активной оконной рамы и панели подписи, но оно не получает другого WM_MDIACTIVATE сообщения.

### <a name="example"></a>Пример

Смотрите пример [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).

## <a name="cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd::MDICascade

Упорядочив все детские окна MDI в каскадном формате.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Определяет каскадный флаг. Только следующий флаг может быть указан: MDITILE_SKIPDISABLED, которая предотвращает инвалидов MDI детских окон от каскада.

### <a name="remarks"></a>Remarks

Первая `MDICascade`версия, без каких-либо параметров, каскады все mDI детские окна, в том числе инвалидов. Вторая версия по желанию не каскадирует отключенные детские окна MDI, если указать MDITILE_SKIPDISABLED для параметра *nType.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

## <a name="cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive

Извлекает текущее активное окно дочернего MDI вместе с флагом, указывающим, максимизируется ли окно дочернего ребенка.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Параметры

*pbMaximized*<br/>
Указатель на значение возврата BOOL. Установить на TRUE по возвращении, если окно максимизируется; в противном случае FALSE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на активное окно ребенка MDI.

### <a name="example"></a>Пример

Смотрите пример [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

## <a name="cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconArrange

Упорядочив все минимизированные окна ребенка документа.

```
void MDIIconArrange();
```

### <a name="remarks"></a>Remarks

Это не влияет на детские окна, которые не минимизированы.

### <a name="example"></a>Пример

Смотрите пример [CMDIFrameWnd::MDICascade](#mdicascade).

## <a name="cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize

Максимизирует указанное окно ребенка MDI.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Очки к окну, чтобы максимизировать.

### <a name="remarks"></a>Remarks

При максимизации окна ребенка Windows изменяет его, чтобы заставить клиентскую область заполнить клиентское окно. Окна размещают меню управления окна ребенка в панели меню кадра, чтобы пользователь мог восстановить или закрыть окно ребенка. Он также добавляет название окна ребенка к названию окна кадра.

Если другое окно ребенка MDI активируется при максимизации действующего в настоящее время окна mDI ребенка, Windows восстанавливает действующий ребенок и максимизирует вновь активированное окно ребенка.

### <a name="example"></a>Пример

Смотрите пример [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

## <a name="cmdiframewndmdinext"></a><a name="mdinext"></a>CMDIFrameWnd::MDINext

Активирует окно ребенка непосредственно за действующим в настоящее время окном ребенка и помещает в настоящее время активное окно ребенка за всеми другими окнами ребенка.

```
void MDINext();
```

### <a name="remarks"></a>Remarks

Если в настоящее время активная детская окно MDI максимизируется, функция участника восстанавливает действующий ребенок и максимизирует вновь активированного ребенка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

## <a name="cmdiframewndmdiprev"></a><a name="mdiprev"></a>CMDIFrameWnd::MDIPrev

Активирует предыдущее окно ребенка и помещает действующее в настоящее время окно ребенка непосредственно за ним.

```
void MDIPrev();
```

### <a name="remarks"></a>Remarks

Если в настоящее время активная детская окно MDI максимизируется, функция участника восстанавливает действующий ребенок и максимизирует вновь активированного ребенка.

## <a name="cmdiframewndmdirestore"></a><a name="mdirestore"></a>CMDIFrameWnd::MDIRestore

Восстанавливает окно ребенка MDI от максимального или минимизированного размера.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно для восстановления.

### <a name="example"></a>Пример

Смотрите пример [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

## <a name="cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu

Заменяет меню окна кадра MDI, всплывающее меню Window или и то, и другое.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*pFrameMenu*<br/>
Определяет меню нового меню окна кадра. Если NULL, меню не изменяется.

*pWindowMenu*<br/>
Определяет меню нового всплывающем меню Window. Если NULL, меню не изменяется.

### <a name="return-value"></a>Возвращаемое значение

Указатель меню окна кадра заменен этим сообщением. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Remarks

После `MDISetMenu`вызова приложение должно позвонить члену `CWnd` [DrawMenuBar,](../../mfc/reference/cwnd-class.md#drawmenubar) чтобы обновить панель меню.

Если этот вызов заменяет всплывающее меню Window, элементы меню «детское окно» MDI удаляются из предыдущего меню «Окно» и добавляются в новое всплывающее меню Window.

Если окно mDI ребенка максимизируется и этот вызов заменяет меню окна кадров MDI, меню управления и элементы восстановления удаляются из предыдущего меню окна кадра и добавляются в новое меню.

Не вызывайте эту функцию участника, если вы используете платформу для управления окнами mDI ребенка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

## <a name="cmdiframewndmditile"></a><a name="mditile"></a>CMDIFrameWnd::MDITile

Упорядочив все детские окна в кафельном формате.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Определяет флаг плитки. Этот параметр может быть любым из следующих флагов:

- MDITILE_HORIZONTAL окна для детей Tiles MDI так, чтобы одно окно было выше другого.

- MDITILE_SKIPDISABLED предотвращает плитку для детей-инвалидов MDI.

- MDITILE_VERTICAL окна милиок MDI так, чтобы одно окно отослававаться рядом с другим.

### <a name="remarks"></a>Remarks

Первая версия `MDITile`, без параметров, плитки окна вертикально под версии Windows 3.1 и позже. Вторая версия плитки окна вертикально или горизонтально, в зависимости от значения параметра *nType.*

### <a name="example"></a>Пример

Смотрите пример [CMDIFrameWnd::MDICascade](#mdicascade).

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
