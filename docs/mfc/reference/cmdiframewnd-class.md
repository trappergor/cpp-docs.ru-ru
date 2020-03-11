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
ms.openlocfilehash: 20d74030cdc90ed2e1a7809c121967e74db21b4a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866569"
---
# <a name="cmdiframewnd-class"></a>Класс CMDIFrameWnd

Предоставляет функции фреймового окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CMDIFrameWnd:: CMDIFrameWnd](#cmdiframewnd)|Создает документ `CMDIFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CMDIFrameWnd:: Креатеклиент](#createclient)|Создает окно МДИКЛИЕНТ Windows для этого `CMDIFrameWnd`. Вызывается функцией `OnCreate` члена `CWnd`.|
|[CMDIFrameWnd:: Креатеневчилд](#createnewchild)|Создает новое дочернее окно.|
|[CMDIFrameWnd:: Жетвиндовменупопуп](#getwindowmenupopup)|Возвращает всплывающее меню окна.|
|[CMDIFrameWnd:: Мдиактивате](#mdiactivate)|Активирует другое дочернее окно MDI.|
|[CMDIFrameWnd:: Мдикаскаде](#mdicascade)|Упорядочивает все дочерние окна в каскадном формате.|
|[CMDIFrameWnd:: Мдижетактиве](#mdigetactive)|Извлекает текущее активное дочернее окно MDI вместе с флагом, указывающим, развернут ли дочерний элемент.|
|[CMDIFrameWnd:: Мдииконарранже](#mdiiconarrange)|Упорядочивает все дочерние окна документа.|
|[CMDIFrameWnd:: Мдимаксимизе](#mdimaximize)|Разворачивает дочернее окно MDI.|
|[CMDIFrameWnd:: Мдинекст](#mdinext)|Активирует дочернее окно сразу за текущим активным дочерним окном и размещает текущее активное дочернее окно позади всех остальных дочерних окон.|
|[CMDIFrameWnd:: Мдипрев](#mdiprev)|Активирует предыдущее дочернее окно и размещает текущее активное дочернее окно непосредственно за ним.|
|[CMDIFrameWnd:: Мдиресторе](#mdirestore)|Восстанавливает дочернее окно MDI из развернутого или минимального размера.|
|[CMDIFrameWnd:: Мдисетмену](#mdisetmenu)|Заменяет меню окна фрейма MDI, всплывающего меню окна или и того и другого.|
|[CMDIFrameWnd:: Мдитиле](#mditile)|Упорядочивает все дочерние окна в мозаичном формате.|

## <a name="remarks"></a>Remarks

Чтобы создать полезное окно фрейма MDI для приложения, создайте класс, производный от `CMDIFrameWnd`. Добавьте переменные члена в производный класс для хранения данных, относящихся к вашему приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Окно фрейма MDI можно создать путем вызова функции-члена [CREATE](../../mfc/reference/cframewnd-class.md#create) или [лоадфраме](../../mfc/reference/cframewnd-class.md#loadframe) `CFrameWnd`.

Перед вызовом `Create` или `LoadFrame`необходимо создать объект окна фрейма в куче с помощью C++ оператора **New** . Перед вызовом `Create` можно также зарегистрировать класс окна с глобальной функцией [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) , чтобы задать стили значков и классов для фрейма.

Используйте функцию члена `Create`, чтобы передать параметры создания кадра в качестве непосредственных аргументов.

`LoadFrame` требует меньше аргументов, чем `Create`, и вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок фрейма, значок, таблицу сочетаний клавиш и меню. Чтобы получить доступ к `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Хотя `MDIFrameWnd` является производным от `CFrameWnd`, класс окна фрейма, производный от `CMDIFrameWnd`, не должен объявляться с `DECLARE_DYNCREATE`.

Класс `CMDIFrameWnd` наследует большую часть своей реализации по умолчанию от `CFrameWnd`. Подробный список этих функций см. в описании класса [CFrameWnd](../../mfc/reference/cframewnd-class.md) . Класс `CMDIFrameWnd` имеет следующие дополнительные возможности.

- Окно фрейма MDI управляет окном МДИКЛИЕНТ, перемещает его в сочетании с панелями управления. Окно клиента MDI — это прямой родительский элемент окон дочернего фрейма MDI. Стили окон WS_HSCROLL и WS_VSCROLL, указанные в `CMDIFrameWnd`, применяются к окну клиента MDI, а не к главному окну фрейма, чтобы пользователь мог прокручивать клиентскую область MDI (например, как в диспетчере программ Windows).

- Окно фрейма MDI владеет меню по умолчанию, которое используется в качестве строки меню при отсутствии активного дочернего окна MDI. При наличии активной дочерней MDI строка меню окна фрейма MDI автоматически заменяется меню дочернего окна MDI.

- Окно фрейма MDI работает совместно с текущим дочерним окном MDI, если оно имеется. Например, сообщения команды делегируются активному в данный момент дочернему элементу MDI до окна фрейма MDI.

- Окно фрейма MDI имеет обработчики по умолчанию для следующих стандартных команд меню "окно":

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- Окно фрейма MDI также имеет реализацию ID_WINDOW_NEW, которая создает новый фрейм и представление в текущем документе. Приложение может переопределять эти реализации команд по умолчанию для настройки обработки окон MDI.

Не используйте C++ оператор **Delete** для уничтожения окна фрейма. Используйте вместо этого `CWnd::DestroyWindow`. `CFrameWnd` реализация `PostNcDestroy` удалит C++ объект при уничтожении окна. Когда пользователь закрывает окно фрейма, обработчик `OnClose` по умолчанию будет вызывать `DestroyWindow`.

Дополнительные сведения о `CMDIFrameWnd`см. в разделе [окна с рамками](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cmdiframewnd"></a>CMDIFrameWnd:: CMDIFrameWnd

Формирует объект `CMDIFrameWnd`.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Remarks

Вызовите функцию-член `Create` или `LoadFrame`, чтобы создать видимое окно фрейма MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>CMDIFrameWnd:: Креатеклиент

Создает клиентское MDI-окно, которое управляет объектами `CMDIChildWnd`.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*лпкреатеструкт*<br/>
Длинный указатель на структуру [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) .

*пвиндовмену*<br/>
Указатель на всплывающее меню окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эту функцию члена следует вызывать, если вы переопределяете функцию члена `OnCreate` напрямую.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>CMDIFrameWnd:: Креатеневчилд

Создает новое дочернее окно.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>Параметры

*пкласс*<br/>
Класс времени выполнения создаваемого дочернего окна.

*нресаурце*<br/>
Идентификатор общих ресурсов, связанных с дочерним окном.

*hMenu*<br/>
Меню дочернего окна.

*хакцел*<br/>
Ускоритель дочернего окна.

### <a name="remarks"></a>Remarks

Эта функция используется для создания дочерних окон окна фрейма MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>CMDIFrameWnd:: Жетвиндовменупопуп

Вызовите эту функцию-член, чтобы получить маркер текущего всплывающего меню с именем "окно" (всплывающее меню с элементами меню для управления окнами MDI).

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Параметры

*хменубар*<br/>
Текущая строка меню.

### <a name="return-value"></a>Возвращаемое значение

Всплывающее меню окна, если оно существует; в противном случае — NULL.

### <a name="remarks"></a>Remarks

Реализация по умолчанию ищет всплывающее меню, содержащее стандартные команды меню "окно", такие как ID_WINDOW_NEW и ID_WINDOW_TILE_HORZ.

Переопределите эту функцию-член, если у вас есть меню окон, в котором не используются стандартные идентификаторы команд меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>CMDIFrameWnd:: Мдиактивате

Активирует другое дочернее окно MDI.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Параметры

*пвндактивате*<br/>
Указывает на дочернее окно MDI, которое должно быть активировано.

### <a name="remarks"></a>Remarks

Эта функция члена отправляет сообщение [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) в активируемое дочернее окно и деактивирует дочернее окно.

Это то же сообщение, которое отправляется, если пользователь изменяет фокус на дочернее окно MDI с помощью мыши или клавиатуры.

> [!NOTE]
>  Дочернее окно MDI активируется независимо от окна фрейма MDI. Когда кадр становится активным, дочернее окно, которое было активировано последним, отправляет [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) сообщение, чтобы нарисовать кадр активного окна и строку заголовка, но не получить еще одно сообщение WM_MDIACTIVATE.

### <a name="example"></a>Пример

См. пример для [CMDIFrameWnd:: жетвиндовменупопуп](#getwindowmenupopup).

##  <a name="mdicascade"></a>CMDIFrameWnd:: Мдикаскаде

Упорядочивает все дочерние окна MDI в формате Cascade.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Задает флаг Cascade. Можно указать только следующий флаг: MDITILE_SKIPDISABLED, который предотвращает каскадное отображение отключенных дочерних окон MDI.

### <a name="remarks"></a>Remarks

Первая версия `MDICascade`без параметров, каскадно размещает все дочерние окна MDI, включая отключенные. Вторая версия при необходимости не позволяет каскадно отключить дочерние окна MDI, если для параметра *nуведомления* задано значение MDITILE_SKIPDISABLED.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>CMDIFrameWnd:: Мдижетактиве

Извлекает текущее активное дочернее окно MDI вместе с флагом, указывающим, развернуто ли дочернее окно.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Параметры

*пбмаксимизед*<br/>
Указатель на возвращаемое логическое значение. Установите значение TRUE для возврата, если окно развернуто. в противном случае — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на активное дочернее окно MDI.

### <a name="example"></a>Пример

См. пример для [CMDIChildWnd:: мдимаксимизе](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdiiconarrange"></a>CMDIFrameWnd:: Мдииконарранже

Упорядочивает все дочерние окна документа.

```
void MDIIconArrange();
```

### <a name="remarks"></a>Remarks

Он не влияет на несведенные дочерние окна.

### <a name="example"></a>Пример

См. пример для [CMDIFrameWnd:: мдикаскаде](#mdicascade).

##  <a name="mdimaximize"></a>CMDIFrameWnd:: Мдимаксимизе

Разворачивает указанное дочернее окно MDI.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно для максимального увеличения.

### <a name="remarks"></a>Remarks

Когда дочернее окно разворачивается, Windows изменяет его размер, чтобы сделать клиентскую область заполнять окно клиента. Windows размещает меню элемента управления дочернего окна в строке меню фрейма, чтобы пользователь мог восстановить или закрыть дочернее окно. Он также добавляет заголовок дочернего окна в заголовок окна фрейма.

Если другое дочернее окно MDI активируется при разворачивании текущего активного дочернего окна MDI, Windows восстанавливает текущий активный дочерний элемент и разворачивает вновь активированное дочернее окно.

### <a name="example"></a>Пример

См. пример для [CMDIChildWnd:: мдимаксимизе](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdinext"></a>CMDIFrameWnd:: Мдинекст

Активирует дочернее окно сразу за текущим активным дочерним окном и размещает текущее активное дочернее окно позади всех остальных дочерних окон.

```
void MDINext();
```

### <a name="remarks"></a>Remarks

Если текущее активное дочернее окно MDI является развернутым, функция-член восстанавливает текущий активный дочерний элемент и разворачивает вновь активированный дочерний элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>CMDIFrameWnd:: Мдипрев

Активирует предыдущее дочернее окно и размещает текущее активное дочернее окно непосредственно за ним.

```
void MDIPrev();
```

### <a name="remarks"></a>Remarks

Если текущее активное дочернее окно MDI является развернутым, функция-член восстанавливает текущий активный дочерний элемент и разворачивает вновь активированный дочерний элемент.

##  <a name="mdirestore"></a>CMDIFrameWnd:: Мдиресторе

Восстанавливает дочернее окно MDI из развернутого или минимального размера.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно для восстановления.

### <a name="example"></a>Пример

См. пример для [CMDIChildWnd:: мдиресторе](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

##  <a name="mdisetmenu"></a>CMDIFrameWnd:: Мдисетмену

Заменяет меню окна фрейма MDI, всплывающего меню окна или и того и другого.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*пфрамемену*<br/>
Задает меню нового меню окна фрейма. Если значение равно NULL, меню не изменяется.

*пвиндовмену*<br/>
Задает меню всплывающего меню нового окна. Если значение равно NULL, меню не изменяется.

### <a name="return-value"></a>Возвращаемое значение

Указатель на меню окна фрейма, замененное этим сообщением. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Remarks

После вызова `MDISetMenu`приложение должно вызвать функцию члена [дравменубар](../../mfc/reference/cwnd-class.md#drawmenubar) из `CWnd`, чтобы обновить строку меню.

Если этот вызов заменяет всплывающее меню окна, элементы меню дочернего окна MDI удаляются из предыдущего меню окна и добавляются во всплывающее меню новое окно.

Если дочернее окно MDI развернуто и этот вызов заменяет меню окна фрейма MDI, меню управления и элементы управления восстановлением удаляются из предыдущего меню окна фрейма и добавляются в новое меню.

Не вызывайте эту функцию-член, если вы используете платформу для управления дочерними окнами MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>CMDIFrameWnd:: Мдитиле

Упорядочивает все дочерние окна в мозаичном формате.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Задает флаг мозаичного заполнения. Этот параметр может иметь один из следующих флагов:

- MDITILE_HORIZONTAL плитки дочерних окон MDI, чтобы одно окно появлялось над другим.

- MDITILE_SKIPDISABLED запрещает мозаичное заполнение отключенных дочерних окон MDI.

- MDITILE_VERTICAL плитки дочерних окон MDI, чтобы одно окно появился рядом с другим.

### <a name="remarks"></a>Remarks

Первая версия `MDITile`, без параметров, располагает окна по вертикали в Windows версий 3,1 и более поздних. Вторая версия окна плиток по вертикали или по горизонтали в зависимости от значения параметра *nуведомления* .

### <a name="example"></a>Пример

См. пример для [CMDIFrameWnd:: мдикаскаде](#mdicascade).

## <a name="see-also"></a>См. также раздел

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример МДИДОКВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
