---
title: Класс CMDIChildWnd | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 995e0ed8dc9d04dd67cd1f4521d4550ccdad36fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390191"
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
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Создает объект `CMDIChildWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDIChildWnd::Create](#create)|Создает дочернее окно Windows MDI, связанные с `CMDIChildWnd` объекта.|
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Возвращает родительский объект фрейма MDI клиентского окна MDI.|
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Активирует этого дочернего окна интерфейса MDI.|
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Уничтожает этого дочернего окна интерфейса MDI.|
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Разворачивает этого дочернего окна интерфейса MDI.|
|[CMDIChildWnd::MDIRestore](#mdirestore)|Восстанавливает этот дочернего окна интерфейса MDI из развернутой или свернутой размер.|
|[CMDIChildWnd::SetHandles](#sethandles)|Задает дескрипторы для ресурсов меню и сочетаний клавиш.|

## <a name="remarks"></a>Примечания

Дочерние окна интерфейса MDI похож типичный фрейме окна, за исключением того, что дочернего окна интерфейса MDI отображается в окне фрейма MDI, а не на рабочем столе. Дочерние окна интерфейса MDI не имеет свои собственные строки меню, но вместо этого использует меню окна фрейма MDI. Платформа автоматически изменяет меню фрейма MDI для представления дочернее окно текущего активного интерфейса MDI.

Чтобы создать полезные дочернего окна интерфейса MDI для вашего приложения, являются производными от класса `CMDIChildWnd`. Добавьте переменные-члены производного класса для хранения данных, к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Для создания дочернего окна MDI тремя способами:

- Напрямую создать его с помощью `Create`.

- Напрямую создать его с помощью `LoadFrame`.

- Косвенно создайте его с помощью шаблона документа.

Перед вызовом метода `Create` или `LoadFrame`, то необходимо создать объект окна фрейма в куче, с помощью C++ **новый** оператор. Перед вызовом `Create` вы также можете зарегистрировать класс окна с [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальную функцию, чтобы задать значок и класс стили рамки.

Используйте `Create` функция-член для передачи в интерпретации аргументов параметры создания фрейма.

`LoadFrame` требуется меньшее количество аргументов, чем `Create`и вместо этого получает большинство его значений по умолчанию из ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню фрейма. Должны быть доступны `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Когда `CMDIChildWnd` объект содержит представления и документы, они создаются косвенно платформой вместо непосредственно в программу самим разработчиком. `CDocTemplate` Объект организует Создание кадра, создавать содержащего представления, а также подключение из представлений в соответствующий документ. Параметры `CDocTemplate` указать конструктор `CRuntimeClass` из трех классов участвует (документа, фрейма и представления). Объект `CRuntimeClass` объект используется платформой для динамического создания новых кадров, при указании пользователем (например, с помощью команды создания файла или MDI окно новой команды).

Класс окна фрейма, производный от `CMDIChildWnd` должна быть объявлена с DECLARE_DYNCREATE в порядке, для правильной работы механизма выше RUNTIME_CLASS.

`CMDIChildWnd` Класс наследует большую часть реализацию по умолчанию от `CFrameWnd`. Подробный список этих функций, обратитесь к [CFrameWnd](../../mfc/reference/cframewnd-class.md) Описание класса. `CMDIChildWnd` Класс имеет следующие дополнительные возможности:

- В сочетании с `CMultiDocTemplate` класса, несколько `CMDIChildWnd` объекты из одного шаблона документа используют то же меню, сохранение системных ресурсов Windows.

- Активной дочернего окна меню MDI полностью заменяет меню Окно области MDI, а заголовок дочернее окно текущего активного MDI добавляется заголовок окно области MDI. Дополнительные примеры MDI дочерние окна функций, реализованных в сочетании с окном фрейма MDI, см. в разделе `CMDIFrameWnd` Описание класса.

Не используйте C++ **удалить** оператор для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow`. `CFrameWnd` Реализация `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно по умолчанию `OnClose` вызовет обработчик `DestroyWindow`.

Дополнительные сведения о `CMDIChildWnd`, см. в разделе [фрейма Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd

Вызов для создания `CMDIChildWnd` объекта.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Примечания

Вызовите `Create` создание видимого окна.

### <a name="example"></a>Пример

  См. в примере [CMDIChildWnd::Create](#create).

##  <a name="create"></a>  CMDIChildWnd::Create

Вызов этой функции-члена для создания дочернего окна многодокументного интерфейса Windows и присоединить его к `CMDIChildWnd` объекта.

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
Указывает на строку нуль-символом, который содержит класс Windows ( [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) структуры). Имя класса может быть любое имя, зарегистрированное [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции. Должен иметь значение NULL для стандартного `CMDIChildWnd`.

*lpszWindowName*<br/>
Указывает символ, завершающаяся нулем строка, представляющая имя окна. Используется в качестве текста для заголовка окна.

*dwStyle*<br/>
Задает окно [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) атрибуты. Стиль WS_CHILD является обязательным.

*Rect*<br/>
Содержит размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового `CMDIChildWnd`.

*pParentWnd*<br/>
Указывает родительского окна. Если значение равно NULL, используется в главное окно приложения.

*pContext*<br/>
Указывает [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

MDI дочернее окно текущего активного кадра можно определить заголовок родительское окно фрейма. Эта функция отключена, отключив бит стиля FWS_ADDTOTITLE дочернего окна фрейма.

Платформа вызывает эту функцию-член в ответ на команду пользователя, чтобы создать дочернее окно, и платформа использует *pContext* параметр для правильного подключения приложения дочернего окна. При вызове `Create`, *pContext* может иметь значение NULL.

### <a name="example"></a>Пример

Пример 1.

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Пример

Пример 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame

Вызывайте эту функцию для возврата родительского фрейма MDI.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительское окно фрейма MDI.

### <a name="remarks"></a>Примечания

Возвращаемый кадр является два родительских элементов, удалены из `CMDIChildWnd` и является родителем окна типа MDICLIENT, который управляет `CMDIChildWnd` объекта. Вызовите [GetParent](../../mfc/reference/cwnd-class.md#getparent) функция-член для возврата `CMDIChildWnd` MDICLIENT родительского объекта для интерпретации как временный `CWnd` указатель.

### <a name="example"></a>Пример

  См. в примере [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate

Вызовите эту функцию-член для активации дочернего окна MDI независимо от окно области MDI.

```
void MDIActivate();
```

### <a name="remarks"></a>Примечания

Когда кадр становится активным, также будут активированы дочернему окну, которое в последний раз была активирована.

### <a name="example"></a>Пример

  См. в примере [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy

Вызовите эту функцию-член для уничтожения дочернего окна MDI.

```
void MDIDestroy();
```

### <a name="remarks"></a>Примечания

Функция-член удаляет заголовок дочернему окну из окна фрейма и деактивирует дочернее окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize

Вызовите эту функцию-член для обеспечения максимальной дочернего окна MDI.

```
void MDIMaximize();
```

### <a name="remarks"></a>Примечания

Если дочернее окно развернуто, Windows изменяет размер, чтобы сделать свою клиентскую область заполнения клиентской области окна фрейма. Windows размещает дочернее окно элемента управления меню в строке меню фрейма, таким образом, пользователь может восстановить или закрытия дочернего окна и добавляет заголовок дочернего окна к заголовку окна фрейма.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore

Вызовите эту функцию-член для восстановления из развернутой или свернутой размер дочернего окна MDI.

```
void MDIRestore();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles

Задает дескрипторы для ресурсов меню и сочетаний клавиш.

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Дескриптор ресурса меню.

*hAccel*<br/>
Дескриптор ресурса сочетаний клавиш.

### <a name="remarks"></a>Примечания

Вызовите эту функцию для задания ресурсов меню и сочетаний клавиш, используемых дочернего окна MDI объекта.

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../visual-cpp-samples.md)<br/>
[Пример MFC MDIDOCVW](../../visual-cpp-samples.md)<br/>
[Пример MFC: SNAPVW](../../visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)
