---
title: Класс CMiniFrameWnd
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: a6fdef34ba5873718caed509100cbe7e905d880d
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693532"
---
# <a name="cminiframewnd-class"></a>Класс CMiniFrameWnd

Представляет фреймовое окно половинной высоты по сравнению с тем, которое стандартно отображается на плавающих панелях инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Создает объект `CMiniFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMiniFrameWnd::Create](#create)|Создает `CMiniFrameWnd` объект после создания.|
|[CMiniFrameWnd::CreateEx](#createex)|Создает `CMiniFrameWnd` объекта (с дополнительными параметрами) после создания.|

## <a name="remarks"></a>Примечания

Эти окна минифрейма ведут себя как обычный фреймов, за исключением того, что они не имеют свернуть или развернуть кнопки или меню и вам необходимо только одним щелчком в системном меню, чтобы отклонить их.

Чтобы использовать `CMiniFrameWnd` объекта, сначала Определите объект. Затем вызовите [создать](#create) функция-член для отображения окна области.

Дополнительные сведения об использовании `CMiniFrameWnd` объектов, см. в статье [закрепления и плавающие панели инструментов](../../mfc/docking-and-floating-toolbars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd

Создает `CMiniFrameWnd` объекта, но не создает окно.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Примечания

Для создания окна, вызовите [CMiniFrameWnd::Create](#create).

##  <a name="create"></a>  CMiniFrameWnd::Create

Создает окно области Windows и присоединяет его к `CMiniFrameWnd` объекта.

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Параметры

*lpClassName*<br/>
Указывает строку нуль-символом, с именем класса Windows. Имя класса может быть любое имя, зарегистрированное с глобальным [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) функции. Если значение равно NULL, класс окна регистрируется для вас платформой. MFC предоставляет класс по умолчанию следующие атрибуты и стили.

- Бит стиля наборы CS_DBLCLKS, которая отправляет дважды щелкните сообщения в процедуру при двойном щелчке мыши.

- Задает бит стиля CS_HREDRAW и CS_VREDRAW, которые настраивают содержимое клиентской области перерисовку при изменении размера окна.

- Устанавливает курсор класса Windows standard IDC_ARROW.

- Задает кисть фона класс значение NULL, поэтому окна не приведет к удалению фоном.

- Задает значок класса standard, машет флаг значок эмблемы Windows.

- Задает размер по умолчанию и положения, окно, как указано в Windows.

*lpWindowName*<br/>
Указывает строку символов с завершающим нулем, которая содержит имя окна.

*dwStyle*<br/>
Указывает атрибуты стиля окна. Они могут включать стандартное окно Стили и один или несколько из следующих специальных стилей:

- MFS_MOVEFRAME позволяет перемещать их, щелкнув любой границы окна, не только заголовок окна области.

- Отключает MFS_4THICKFRAME изменения размера окна области.

- MFS_SYNCACTIVE синхронизирует активации окна области для активации его родительского окна.

- MFS_THICKFRAME позволяет разрешить выйдет как содержимое клиентской области окна области.

- Отключает MFS_BLOCKSYSMENU доступ к меню «system» и меню элемента управления и преобразует их в часть заголовка (заголовок).

См. в разделе [CWnd::Create](../../mfc/reference/cwnd-class.md#create) описание значений стилей окон невозможно. Обычно используется для окон области комбинация будет WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU.

*Rect*<br/>
Объект `RECT` структуру, указав нужные размеры окна.

*pParentWnd*<br/>
Указатель на родительское окно. Используйте NULL для окон верхнего уровня.

*nID*<br/>
Если окно области создается как дочернего окна, это идентификатор дочернего элемента управления; в противном случае 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Create` Инициализирует имя класса окна и имя окна и регистрирует значения по умолчанию для его стиль и родительский.

##  <a name="createex"></a>  CMiniFrameWnd::CreateEx

Создает объект `CMiniFrameWnd`.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Задает расширенный стиль `CMiniFrameWnd` создания. Применения любого из [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) в окно.

*lpClassName*<br/>
Указывает на строку нуль-символом, который содержит класс Windows ( [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) структуры). Имя класса может быть любое имя, зарегистрированное с глобальным [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) функции или какие-либо имена предопределенных класс элемента управления. Он не должен иметь значение NULL.

*lpWindowName*<br/>
Указывает строку символов с завершающим нулем, которая содержит имя окна.

*dwStyle*<br/>
Указывает атрибуты стиля окна. См. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [CWnd::Create](../../mfc/reference/cwnd-class.md#create) описание возможных значений.

*Rect*<br/>
Размер и положение окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указывает родительский объект окна.

*nID*<br/>
Идентификатор дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CreateEx` Параметры указывают WNDCLASS, стиль окна и (необязательно) начальное положение и размер окна. `CreateEx` также указывает окна родительского (если таковые имеются) и идентификатор.

Когда `CreateEx` выполняет, Windows отправляет [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) сообщения в окне.

Чтобы расширить обработку сообщения по умолчанию, являются производными от класса `CMiniFrameWnd`, добавить схему сообщений к новому классу и обеспечивает функции-члены выше сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.

Переопределить дальнейшей `On` *сообщение* обработчиков для обеспечения дополнительной функциональности к своему производному классу сообщений.

Если стиль WS_VISIBLE, Windows отправляет окна все необходимые для активации и отображение окна сообщения. Если стиль окна задает заголовок окна, заголовок окна указывает *lpszWindowName* параметр отображается в заголовке окна.

*DwStyle* параметр может быть любое сочетание [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

Старых средств стиля палитры панели элементов windows больше не поддерживаются. Старый стиль, который не имел кнопка закрытия «X», был поддерживается при запуске приложения MFC в предыдущих версиях Windows, но больше не поддерживается в Visual C++ .NET. Теперь поддерживается только новый стиль WS_EX_TOOLWINDOW; Описание этого стиля, см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>См. также

[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
