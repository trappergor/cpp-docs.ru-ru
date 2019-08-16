---
title: Класс Кминифрамевнд
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
ms.openlocfilehash: 45b4698cc70487a6c3fe1470fe27f7b5c4f95402
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504593"
---
# <a name="cminiframewnd-class"></a>Класс Кминифрамевнд

Представляет фреймовое окно половинной высоты по сравнению с тем, которое стандартно отображается на плавающих панелях инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кминифрамевнд:: Кминифрамевнд](#cminiframewnd)|Создает объект `CMiniFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кминифрамевнд:: Create](#create)|`CMiniFrameWnd` Создает объект после создания.|
|[Кминифрамевнд:: Креатикс](#createex)|`CMiniFrameWnd` Создает объект (с дополнительными параметрами) после создания.|

## <a name="remarks"></a>Примечания

Эти окна с мини-кадрами ведут себя как обычные окна фрейма, за исключением того, что у них нет кнопок или меню, и для их закрытия достаточно щелкнуть только один щелчок в системном меню.

Чтобы использовать `CMiniFrameWnd` объект, сначала определите объект. Затем вызовите функцию [создания](#create) члена, чтобы отобразить окно с мини-рамкой.

Дополнительные сведения об использовании `CMiniFrameWnd` объектов см. в статье закрепление [и плавающие панели инструментов](../../mfc/docking-and-floating-toolbars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cminiframewnd"></a>Кминифрамевнд:: Кминифрамевнд

`CMiniFrameWnd` Создает объект, но не создает окно.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Примечания

Чтобы создать окно, вызовите метод [кминифрамевнд:: Create](#create).

##  <a name="create"></a>Кминифрамевнд:: Create

Создает окно мини-кадра Windows и прикрепляет его к `CMiniFrameWnd` объекту.

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

*лпкласснаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая именует класс Windows. Имя класса может быть любым именем, зарегистрированным в глобальной функции [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) . Если значение равно NULL, то класс Window будет зарегистрирован для вас платформой. MFC предоставляет классу по умолчанию следующие стили и атрибуты:

- Задает бит стиля CS_DBLCLKS, который отправляет сообщения двойного щелчка в процедуру окна, когда пользователь дважды щелкает мышью.

- Задает биты Style CS_HREDRAW и CS_VREDRAW, направляющие содержимое клиентской области для перерисовки при изменении размера окна.

- Устанавливает курсор класса в IDC_ARROW Windows Standard.

- Задает для кисти фона класса значение NULL, поэтому окно не будет очищать свой фон.

- Задает значок класса Standard, машет значок логотипа Windows.

- Задает для окна размер и расположение по умолчанию, как указано в Windows.

*лпвиндовнаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая содержит имя окна.

*двстиле*<br/>
Задает атрибуты стиля окна. К ним могут относиться стандартные стили окон и один или несколько следующих специальных стилей:

- MFS_MOVEFRAME позволяет перемещать окно в рамке, щелкая любую границу окна, а не только заголовок.

- MFS_4THICKFRAME отключает изменение размера окна мини-кадра.

- MFS_SYNCACTIVE синхронизирует активацию окна мини-кадра с активацией его родительского окна.

- MFS_THICKFRAME позволяет размер окна мини-фрейма быть небольшим по размеру содержимого клиентской области.

- MFS_BLOCKSYSMENU отключает доступ к системному меню и меню управления и преобразует их в часть заголовка (заголовок окна).

Описание возможных значений стиля окна см. в разделе [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) . Типичным сочетанием, используемым для окон мини-&#124;кадров&#124;, является WS_POPUP WS_CAPTION WS_SYSMENU.

*rect*<br/>
`RECT` Структура, указывающая нужные размеры окна.

*ппарентвнд*<br/>
Указывает на родительское окно. Для окон верхнего уровня используйте значение NULL.

*nID*<br/>
Если окно мини-кадра создано как дочернее окно, это идентификатор дочернего элемента управления; в противном случае — 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Create`Инициализирует имя класса окна и имя окна и регистрирует значения по умолчанию для его стиля и родителя.

##  <a name="createex"></a>Кминифрамевнд:: Креатикс

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

*двексстиле*<br/>
Задает расширенный стиль создаваемого объекта `CMiniFrameWnd` . Примените к окну любой из [расширенных стилей окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) .

*лпкласснаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая именует класс Windows (структуру [вндкласс](/windows/win32/api/winuser/ns-winuser-wndclassw) ). Имя класса может быть любым именем, зарегистрированным в глобальной функции [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) , или любыми предопределенными именами классов элементов управления. Оно не должно иметь значение NULL.

*лпвиндовнаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая содержит имя окна.

*двстиле*<br/>
Задает атрибуты стиля окна. Описание возможных значений см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) .

*rect*<br/>
Размер и расположение окна в координатах клиента *ппарентвнд*.

*ппарентвнд*<br/>
Указывает на объект родительского окна.

*nID*<br/>
Идентификатор дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CreateEx` Параметры определяют вндкласс, стиль окна и (необязательно) начальную точку и размер окна. `CreateEx`также указывает родительский элемент окна (если он есть) и идентификатор.

Когда `CreateEx` выполняется, Windows отправляет сообщения [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) в окно.

Чтобы расширить обработку сообщений по умолчанию, создайте производный класс `CMiniFrameWnd`от, добавьте к новому классу схему сообщений и предоставьте функции-члены для приведенных выше сообщений. Переопределение `OnCreate`, например, для выполнения необходимой инициализации нового класса.

Переопределите `On`дополнительные обработчики сообщений *сообщений* , чтобы добавить дополнительные функции в производный класс.

Если задан стиль WS_VISIBLE, Windows отправляет окно все сообщения, необходимые для активации и отображения окна. Если стиль окна задает строку заголовка, заголовок окна, на который указывает параметр *лпсзвиндовнаме* , отображается в строке заголовка.

Параметр *двстиле* может быть любым сочетанием [стилей окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

Старые окна панели элементов палитры стилей больше не поддерживаются. Старый стиль, который не имеет кнопки закрытия "X", поддерживался при запуске приложения MFC в предыдущих версиях Windows, но больше не поддерживается в Visual C++.NET. Теперь поддерживается только новый стиль WS_EX_TOOLWINDOW. Описание этого стиля см. в разделе [Расширенные стили окон](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>См. также

[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
