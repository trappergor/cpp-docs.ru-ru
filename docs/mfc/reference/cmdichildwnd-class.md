---
title: Класс CMDIChildWnd
ms.date: 11/04/2016
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
ms.openlocfilehash: 0fbcb47f3148b72a3155e7c17cc913d652c70c2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370086"
---
# <a name="cmdichildwnd-class"></a>Класс CMDIChildWnd

Предоставляет функции дочернего окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Формирует объект `CMDIChildWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDIChildWnd::Создание](#create)|Создает окно ребенка Windows MDI, связанное с объектом. `CMDIChildWnd`|
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Возвращает родительский mDI-рамку окна клиента MDI.|
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Активирует это окно ребенка MDI.|
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Уничтожает это детское окно MDI.|
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Максимизирует это окно ребенка MDI.|
|[CMDIChildWnd::MDIRestore](#mdirestore)|Восстанавливает это окно ребенка MDI от максимального или минимизированного размера.|
|[CMDIChildWnd::Set](#sethandles)|Устанавливает ручки для ресурсов меню и ускорителей.|

## <a name="remarks"></a>Remarks

Детское окно MDI очень похоже на обычное окно кадра, за исключением того, что окно ребенка MDI отображается внутри окна кадра MDI, а не на рабочем столе. Окно ребенка MDI не имеет собственного бара меню, но вместо этого разделяет меню окна кадра MDI. Платформа автоматически изменяет меню кадра MDI, чтобы представить в настоящее время активное окно ребенка MDI.

Чтобы создать полезное окно для детей MDI `CMDIChildWnd`для вашего приложения, выберите класс из . Добавление переменных членов в полученный класс для хранения данных, специфичные для приложения. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Существует три способа построения окна для детей MDI:

- Непосредственно построить `Create`его с помощью .

- Непосредственно построить `LoadFrame`его с помощью .

- Косвенно построить его через шаблон документа.

Перед `Create` вызовом `LoadFrame`или с помощью **нового** оператора c-new operator необходимо построить объект окна кадра на куче. Перед `Create` вызовом вы также можете зарегистрировать класс окон с глобальной функцией [AfxRegisterWndClass,](application-information-and-management.md#afxregisterwndclass) чтобы установить значок и стили класса для кадра.

Используйте `Create` функцию члена, чтобы передать параметры создания кадра в качестве непосредственных аргументов.

`LoadFrame`требует меньше аргументов, чем, `Create`и вместо этого извлекает большую часть значений по умолчанию из ресурсов, включая подпись кадра, значок, таблицу акселератора и меню. Чтобы быть `LoadFrame`доступными, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Когда `CMDIChildWnd` объект содержит представления и документы, они создаются косвенно рамочным, а не непосредственно программистом. Объект `CDocTemplate` организует создание кадра, создание содержащих представлений и соединение представлений с соответствующим документом. Параметры конструктора `CDocTemplate` определяют `CRuntimeClass` три класса (документ, кадр и представление). Объект `CRuntimeClass` используется инфраструктурой для динамического создания новых кадров при указании пользователем (например, с помощью команды File New или новой команды MDI Window).

Класс окна кадра, `CMDIChildWnd` полученный из, должен быть объявлен с DECLARE_DYNCREATE для того, чтобы вышеуказанный механизм RUNTIME_CLASS работал правильно.

Класс `CMDIChildWnd` наследует большую часть `CFrameWnd`своей реализации по умолчанию от . Для получения подробного списка этих функций, пожалуйста, обратитесь к описанию класса [CFrameWnd.](../../mfc/reference/cframewnd-class.md) Класс `CMDIChildWnd` имеет следующие дополнительные функции:

- В сочетании `CMultiDocTemplate` с `CMDIChildWnd` классом несколько объектов из одного и того же шаблона документов разделяют одно и то же меню, экономя ресурсы системы Windows.

- В настоящее время активное меню окна для детей MDI полностью заменяет меню окна окна кадра MDI, и подпись к действующему в настоящее время окну ребенка MDI добавляется к подписи окна кадра MDI. Дополнительные примеры функций окна детского окна MDI, которые реализуются в сочетании с окном кадра MDI, см. `CMDIFrameWnd`

Не используйте оператора **удаления** C's для уничтожения окна рамы. Используйте вместо этого `CWnd::DestroyWindow`. Реализация `CFrameWnd` `PostNcDestroy` будет удалять объект C's при уничтожении окна. Когда пользователь закрывает окно кадра, `OnClose` обработчик по умолчанию вызовет. `DestroyWindow`

Для получения `CMDIChildWnd`дополнительной информации о, см. [Frame Windows](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd

Вызов для `CMDIChildWnd` построения объекта.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Remarks

Вызов `Create` для создания видимого окна.

### <a name="example"></a>Пример

  Смотрите пример [CMDIChildWnd::Создание](#create).

## <a name="cmdichildwndcreate"></a><a name="create"></a>CMDIChildWnd::Создание

Вызовите эту функцию участника, чтобы создать окно `CMDIChildWnd` ребенка Windows MDI и прикрепите его к объекту.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CMDIFrameWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Указывает на строку символов с нулевым завершением, которая называет класс Windows (структура [WNDCLASS).](/windows/win32/api/winuser/ns-winuser-wndclassw) Имя класса может быть любым именем, зарегистрированным в глобальной функции [AfxRegisterWndClass.](application-information-and-management.md#afxregisterwndclass) Должно быть NULL `CMDIChildWnd`для стандарта .

*lpszWindowName*<br/>
Указывает на строку символов с нулевым завершением, представляющую имя окна. Используется в качестве текста для заголовка бара.

*dwStyle*<br/>
Определяет атрибуты [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) окна. Требуется стиль WS_CHILD.

*rect*<br/>
Содержит размер и положение окна. Значение `rectDefault` позволяет Windows указать размер и `CMDIChildWnd`положение нового.

*pParentWnd*<br/>
Определяет родителей окна. Если NULL используется основное окно приложения.

*pContext*<br/>
Определяет структуру [CCreateContext.](../../mfc/reference/ccreatecontext-structure.md) Этот параметр может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

В настоящее время активное окно детской рамы MDI может определить подпись окна родительской рамы. Эта функция отключена, выключив FWS_ADDTOTITLE немного стиля окна детской рамы.

Платформа вызывает эту функцию элемента в ответ на команду пользователя для создания окна ребенка, а фреймворк использует параметр *pContext* для правильного подключения окна ребенка к приложению. Когда вы `Create` *звоните, pContext* может быть NULL.

### <a name="example"></a>Пример

Пример 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Пример

Пример 2.

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame

Вызовите эту функцию, чтобы вернуть родительский кадр MDI.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно родительской рамы MDI.

### <a name="remarks"></a>Remarks

Возвращается кадр, два родителя удалены из `CMDIChildWnd` окна типа MDICLIENT, `CMDIChildWnd` управляющего объектом. Позвоните в функцию участника [GetParent,](../../mfc/reference/cwnd-class.md#getparent) чтобы вернуть непосредственного родителя MDICLIENT `CMDIChildWnd` объекта в качестве временного `CWnd` указателя.

### <a name="example"></a>Пример

  Смотрите пример [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIChildWnd::MDIActivate

Вызовите эту функцию участника, чтобы активировать окно ребенка MDI независимо от окна кадра MDI.

```
void MDIActivate();
```

### <a name="remarks"></a>Remarks

Когда кадр становится активным, будет активировано и окно ребенка, которое было активировано в последний раз.

### <a name="example"></a>Пример

  Смотрите пример [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy

Вызовите эту функцию участника, чтобы уничтожить окно ребенка MDI.

```
void MDIDestroy();
```

### <a name="remarks"></a>Remarks

Функция участника удаляет название окна ребенка из окна кадра и отключает окно ребенка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize

Вызов исчерпайте эту функцию участника, чтобы максимизировать окно ребенка MDI.

```
void MDIMaximize();
```

### <a name="remarks"></a>Remarks

При максимизации окна ребенка Windows изменяет его, чтобы заставить клиентскую область заполнить клиентскую область окна кадра. Окна размещают меню управления окна ребенка в панели меню кадра, чтобы пользователь мог восстановить или закрыть окно ребенка, и добавили название окна ребенка к названию окна кадра.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a>CMDIChildWnd::MDIRestore

Вызов ими функции участника для восстановления окна ребенка MDI с максимального или минимизированного размера.

```
void MDIRestore();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a>CMDIChildWnd::Set

Устанавливает ручки для ресурсов меню и ускорителей.

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Ручка ресурса меню.

*hAccel*<br/>
Ручка ресурса ускорителя.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы настроить меню и ресурсы ускорителя, используемые объектом окна ребенка MDI.

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)
