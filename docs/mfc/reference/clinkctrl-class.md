---
title: Класс CLinkCtrl
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: aa1f630b448c60a0eeb6a905ed6eef6f84a2ff8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372258"
---
# <a name="clinkctrl-class"></a>Класс CLinkCtrl

Предоставляет функциональные возможности стандартного элемента управления SysLink Windows.

## <a name="syntax"></a>Синтаксис

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CLinkCtrl:CLinkCtrl](#clinkctrl)|Формирует объект `CLinkCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CLinkCtrl::Создание](#create)|Создает элемент управления ссылкой и `CLinkCtrl` прикрепляет его к объекту.|
|[CLinkCtrl::CreateEx](#createex)|Создает управление ссылкой с расширенными стилями и прикрепляет его к объекту. `CLinkCtrl`|
|[CLinkCtrl:GetIdealHeight](#getidealheight)|Получает идеальную высоту управления ссылкой.|
|[CLinkCtrl:GetIdealSize](#getidealsize)|Вычисляет предпочтительную высоту текста ссылки для текущего управления ссылкой, в зависимости от указанной ширины ссылки.|
|[CLinkCtrl:GetItem](#getitem)|Извлекает состояния и атрибуты элемента управления ссылками.|
|[CLinkCtrl:GetItemID](#getitemid)|Извлекает идентификатор элемента управления ссылками.|
|[CLinkCtrl:GetItemState](#getitemstate)|Извлекает состояние элемента управления ссылкой.|
|[CLinkCtrl:GetItemUrl](#getitemurl)|Извлекает URL-адрес, представленный элементом управления ссылками.|
|[CLinkCtrl::HitTest](#hittest)|Определяет, нажал ли пользователь указанную ссылку.|
|[CLinkCtrl:SetItem](#setitem)|Устанавливает состояния и атрибуты элемента управления ссылками.|
|[CLinkCtrl:SetItemID](#setitemid)|Устанавливает идентификатор элемента управления ссылками.|
|[CLinkCtrl:SetItemState](#setitemstate)|Устанавливает состояние элемента управления ссылкой.|
|[CLinkCtrl:SetItemUrl](#setitemurl)|Устанавливает URL, представленный элементом управления ссылками.|

## <a name="remarks"></a>Remarks

"Управление ссылками" обеспечивает удобный способ встраивать гипертекстовые ссылки в окно. Фактический элемент управления — это окно, которое отображает размеченный текст и запускает соответствующие приложения, когда пользователь нажимает на встроенную ссылку. Несколько ссылок поддерживаются в рамках одного элемента управления и могут быть доступны с помощью нулевого индекса.

Этот элемент управления `CLinkCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows XP и позже.

Для получения дополнительной информации смотрите [Управление SysLink](/windows/win32/Controls/syslink-overview) в SDK Windows.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="clinkctrlclinkctrl"></a><a name="clinkctrl"></a>CLinkCtrl:CLinkCtrl

Формирует объект `CLinkCtrl`.

```
CLinkCtrl();
```

## <a name="clinkctrlcreate"></a><a name="create"></a>CLinkCtrl::Создание

Создает элемент управления ссылкой и `CLinkCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszLinkMarkup*<br/>
Указатель на строку с нулевым завершением, содержащую размеченный текст для отображения. Для получения дополнительной информации смотрите раздел "Markup и ссылка доступа" в теме [Обзор SysLink управления](/windows/win32/Controls/syslink-overview).

*dwStyle*<br/>
Определяет стиль управления ссылкой. Примените любую комбинацию стилей управления. Для получения дополнительной `Windows SDK` информации можно ознакомиться с [общими стилями управления.](/windows/win32/Controls/common-control-styles)

*rect*<br/>
Определяет размер и положение управления ссылкой. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Определяет родительское окно управления ссылкой. Она не должна быть NULL.

*nID*<br/>
Уведомляет идентификатор управления ссылкой.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если инициализация была успешной; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Вы строите `CLinkCtrl` объект в два этапа. Сначала позвоните конструктору, `Create`а затем вызов , который создает `CLinkCtrl` управление ссылкой и прикрепляет его к объекту. Если вы хотите использовать расширенные стили `Create`окон с вашим управлением, позвоните [cLinkCtrl::CreateEx](#createex) вместо .

Вторая форма `Create` метода амортизирована. Используйте первую форму, которая определяет параметр *lpszLinkMarkup.*

### <a name="example"></a>Пример

Следующий пример кода определяет две `m_Link1` переменные, названные и `m_Link2`, которые используются для доступа к двум элементам управления ссылками.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>Пример

Следующий пример кода создает один элемент управления ссылками на основе расположения другого элемента управления ссылками. Загрузчик ресурсов создает первый элемент управления ссылками при запуске приложения. Когда приложение входит в метод OnInitDialog, вы создаете второй элемент управления ссылкой относительно позиции управления первой ссылкой. Затем вы изменяете размер второго элемента управления ссылками, чтобы соответствовать отображению текста.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

## <a name="clinkctrlcreateex"></a><a name="createex"></a>CLinkCtrl::CreateEx

Создает управление ссылкой с расширенными стилями и прикрепляет его к объекту. `CLinkCtrl`

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>Параметры

*lpszLinkMarkup*<br/>
Указатель на строку с нулевым завершением, содержащую размеченный текст для отображения. Для получения дополнительной информации смотрите раздел "Markup и ссылка доступа" в теме [Обзор SysLink управления](/windows/win32/Controls/syslink-overview).

*dwExStyle*<br/>
Определяет расширенный стиль управления ссылкой. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Определяет стиль управления ссылкой. Примените любую комбинацию стилей управления. Для получения дополнительной информации [см.](/windows/win32/Controls/common-control-styles)

*rect*<br/>
Определяет размер и положение управления ссылкой. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Определяет родительское окно управления ссылкой. Она не должна быть NULL.

*nID*<br/>
Уведомляет идентификатор управления ссылкой.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если инициализация была успешной; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` вместо [создания](#create) для применения расширенных констант стиля Windows.

Вторая форма `CreateEx` метода амортизирована. Используйте первую форму, которая определяет параметр *lpszLinkMarkup.*

## <a name="clinkctrlgetidealheight"></a><a name="getidealheight"></a>CLinkCtrl:GetIdealHeight

Получает идеальную высоту управления ссылкой.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идеальная высота управления, в пикселях.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [LM_GETIDEALHEIGHT,](/windows/win32/Controls/lm-getidealheight)как описано в SDK Windows.

## <a name="clinkctrlgetidealsize"></a><a name="getidealsize"></a>CLinkCtrl:GetIdealSize

Вычисляет предпочтительную высоту текста ссылки для текущего управления ссылкой, в зависимости от указанной ширины ссылки.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*cxMaxWidth*|(в) Максимальная ширина соединения, в пикселях.|
|(ваут) \* *pSize*|Указатель на структуру [Windows СИЗЕ.](/windows/win32/api/windef/ns-windef-size) Когда этот метод *cy* возвращается, `SIZE` cy член структуры содержит идеальную высоту текста ссылки для ширины текста ссылки, которая *указана cxMaxWidth.* *Cx* член структуры содержит ширину текста ссылки, которая действительно необходима.|

### <a name="return-value"></a>Возвращаемое значение

Предпочтительная высота текста ссылки, в пикселях. Значение возврата такое же, как и значение `SIZE` участника *cy* структуры.

### <a name="remarks"></a>Remarks

Например, пример `GetIdealSize` метода см. [CLinkCtrl::Create](#create)

Этот метод отправляет [LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize) сообщение, которое описано в SDK Windows.

## <a name="clinkctrlgetitem"></a><a name="getitem"></a>CLinkCtrl:GetItem

Извлекает состояния и атрибуты элемента управления ссылками.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на структуру [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) для получения информации о товаре.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [LM_GETITEM,](/windows/win32/Controls/lm-getitem)как описано в SDK Windows.

## <a name="clinkctrlgetitemid"></a><a name="getitemid"></a>CLinkCtrl:GetItemID

Извлекает идентификатор элемента управления ссылками.

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылками.

*strID*<br/>
Объект [CStringT,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий идентификатор указанного элемента.

*szID*<br/>
Строка с нулевым завершением, содержащая идентификатор указанного элемента.

*cchID*<br/>
Размер символов буфера *szID.*

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

> [!NOTE]
> Эта функция также возвращает FALSE, если буфер *szID или strID* меньше, чем MAX_LINKID_TEXT.

### <a name="remarks"></a>Remarks

Извлекает идентификатор определенного элемента управления ссылками. Для получения дополнительной информации смотрите сообщение Win32 [LM_GETITEM](/windows/win32/Controls/lm-getitem) в SDK Windows.

## <a name="clinkctrlgetitemstate"></a><a name="getitemstate"></a>CLinkCtrl:GetItemState

Извлекает состояние элемента управления ссылкой.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылками.

*pnState*<br/>
Значение указанного элемента состояния.

*stateMask*<br/>
Комбинация флагов, описывающих, какой элемент состояния получить. Список значений можно узнать `state` в структуре [LITEM.](/windows/win32/api/commctrl/ns-commctrl-litem) Разрешенные элементы идентичны тем, которые разрешены в `state`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Извлекает значение указанного элемента состояния конкретного элемента управления ссылками. Для получения дополнительной информации смотрите сообщение Win32 [LM_GETITEM](/windows/win32/Controls/lm-getitem) в SDK Windows.

## <a name="clinkctrlgetitemurl"></a><a name="getitemurl"></a>CLinkCtrl:GetItemUrl

Извлекает URL-адрес, представленный элементом управления ссылками.

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылками.

*strUrl*<br/>
Объект [CStringT,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий URL, представленный указанным элементом

*szUrl*<br/>
Строка с нулевым завершением, содержащая URL-адрес, представленный указанным элементом

*cchUrl*<br/>
Размер символов буфера *szURL.*

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

> [!NOTE]
> Эта функция также возвращает FALSE, если буфер *szUrl или strUrl* меньше, чем MAX_LINKID_TEXT.

### <a name="remarks"></a>Remarks

Извлекает URL-адрес, представленный указанным элементом управления ссылками. Для получения дополнительной информации смотрите сообщение Win32 [LM_GETITEM](/windows/win32/Controls/lm-getitem) в SDK Windows.

## <a name="clinkctrlhittest"></a><a name="hittest"></a>CLinkCtrl::HitTest

Определяет, нажал ли пользователь указанную ссылку.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>Параметры

*phti*<br/>
Указатель на `LHITTESTINFO` структуру, содержащую любую информацию о ссылке, на что нажал пользователь.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [LM_HITTEST,](/windows/win32/Controls/lm-hittest)как описано в SDK Windows.

## <a name="clinkctrlsetitem"></a><a name="setitem"></a>CLinkCtrl:SetItem

Устанавливает состояния и атрибуты элемента управления ссылками.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на структуру [LITEM,](/windows/win32/api/commctrl/ns-commctrl-litem) содержащую информацию для установки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [LM_SETITEM,](/windows/win32/Controls/lm-setitem)как описано в SDK Windows.

## <a name="clinkctrlsetitemid"></a><a name="setitemid"></a>CLinkCtrl:SetItemID

Извлекает идентификатор элемента управления ссылками.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылками.

*szID*<br/>
Строка с нулевым завершением, содержащая идентификатор указанного элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Устанавливает идентификатор определенного элемента управления ссылками. Для получения дополнительной информации смотрите сообщение Win32 [LM_SETITEM](/windows/win32/Controls/lm-setitem) в SDK Windows.

## <a name="clinkctrlsetitemstate"></a><a name="setitemstate"></a>CLinkCtrl:SetItemState

Извлекает состояние элемента управления ссылкой.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылками.

*pnState*<br/>
Значение заданного элемента состояния.

*stateMask*<br/>
Комбинация флагов, описывающих набор элемента состояния. Список значений можно узнать `state` в структуре [LITEM.](/windows/win32/api/commctrl/ns-commctrl-litem) Разрешенные элементы идентичны тем, которые разрешены в `state`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Устанавливает значение указанного элемента состояния конкретного элемента управления ссылками. Для получения дополнительной информации смотрите сообщение Win32 [LM_SETITEM](/windows/win32/Controls/lm-setitem) в SDK Windows.

## <a name="clinkctrlsetitemurl"></a><a name="setitemurl"></a>CLinkCtrl:SetItemUrl

Устанавливает URL, представленный элементом управления ссылками.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылками.

*szUrl*<br/>
Строка с нулевым завершением, содержащая URL-адрес, представленный указанным элементом

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Устанавливает URL, представленный указанным элементом управления ссылками. Для получения дополнительной информации смотрите сообщение Win32 [LM_SETITEM](/windows/win32/Controls/lm-setitem) в SDK Windows.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)
