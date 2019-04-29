---
title: Класс CMFCMenuButton
ms.date: 11/04/2016
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: cbdf4005ee1a0249e7ed2b5f1d50621fb951f64f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388427"
---
# <a name="cmfcmenubutton-class"></a>Класс CMFCMenuButton

Кнопку, которая отображает контекстное меню и сообщает, какие пункты выбирает в меню пользователь.

## <a name="syntax"></a>Синтаксис

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Создает объект `CMFCMenuButton`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Вызывается платформой для преобразования сообщений окна перед их отправкой. (Переопределяет `CMFCButton::PreTranslateMessage`.)|
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Изменение размера кнопки в зависимости от размера текста и изображений.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Указывает, следует ли для отображения всплывающего меню системы по умолчанию или использовать [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Указывает, будет ли отображаться всплывающее меню под и справа от кнопки.|
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Указывает ли кнопки меню изменяет свое состояние после отпускании кнопки.|
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Дескриптор вложенного меню Windows.|
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Идентификатор, который указывает, какой элемент пользователь выбрал во всплывающем меню.|

## <a name="remarks"></a>Примечания

`CMFCMenuButton` Класс является производным от [класс CMFCButton](../../mfc/reference/cmfcbutton-class.md) который в свою очередь, наследуется от [класс CButton](../../mfc/reference/cbutton-class.md). Таким образом, можно использовать `CMFCMenuButton` в коде можно использовать так же `CButton`.

При создании `CMFCMenuButton`, необходимо передать дескриптор связанного во всплывающее меню. Затем вызовите функцию `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent` проверяет, что размер кнопки достаточно для включения стрелка, указывающая на месте, где будет отображаться всплывающее окно — а именно, нижней или справа от кнопки.

## <a name="example"></a>Пример

Ниже приведен пример, как задавать дескриптор меню, подключенное к кнопке, изменить размер кнопки в зависимости от размера текста и изображений и задавать контекстном меню, которое отображается платформой. Этот фрагмент кода является частью [пример новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxmenubutton.h

##  <a name="cmfcmenubutton"></a>  CMFCMenuButton::CMFCMenuButton

Создает новый [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) объекта.

```
CMFCMenuButton();
```

##  <a name="m_bosmenu"></a>  CMFCMenuButton::m_bOSMenu

Платформа переменную-член типа Boolean, указывающее, какие всплывающего меню отображает.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Примечания

Если `m_bOSMenu` имеет значение TRUE, платформа вызывает наследуемого `TrackPopupMenu` метод для этого объекта. В противном случае вызывается платформой [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).

##  <a name="m_brightarrow"></a>  CMFCMenuButton::m_bRightArrow

Переменная член типа Boolean, указывающее расположение всплывающего меню.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Примечания

Когда пользователь нажимает кнопку меню, приложение показывает всплывающего меню. Платформа будет отображаться всплывающее меню под кнопкой или справа от кнопки. Эта кнопка также имеет маленькую стрелку, которая указывает, где отображаются во всплывающем меню. Если `m_bRightArrow` имеет значение TRUE, платформа отображает всплывающего меню справа от кнопки. В противном случае отображается во всплывающем меню под кнопкой.

##  <a name="m_bstaypressed"></a>  CMFCMenuButton::m_bStayPressed

Переменную-член типа Boolean, указывающее, отображается ли кнопка меню нажатии, когда пользователь делает выбор в раскрывающемся меню.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Примечания

Если `m_bStayPressed` члена имеет значение FALSE, кнопку меню не становятся нажата при нажатии пользователем кнопки. Таким образом платформа отображает только во всплывающем меню.

Если `m_bStayPressed` члена имеет значение TRUE, становится нажата кнопка меню, когда пользователь нажимает кнопку. Он остается нажатой до, после закрытия всплывающего меню, путем выбора или отмены.

##  <a name="m_hmenu"></a>  CMFCMenuButton::m_hMenu

Дескриптор для вложенного меню.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Примечания

Платформа отображает меню, обозначается переменную-член, когда пользователь нажимает кнопку меню.

##  <a name="m_nmenuresult"></a>  CMFCMenuButton::m_nMenuResult

Целое число, указывающее, какой элемент пользователь выбирает во всплывающем меню.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Примечания

Значение этой переменной-члена равно нулю, если пользователь отменяет меню без выбора или если возникает ошибка.

##  <a name="pretranslatemessage"></a>  CMFCMenuButton::PreTranslateMessage

Вызывается платформой для преобразования сообщений окна перед их отправкой.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
[in] Указывает на [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) структуру, содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение было преобразовано и не удается отправить; 0, если сообщение не было преобразовано и должно быть перенаправлено.

### <a name="remarks"></a>Примечания

##  <a name="sizetocontent"></a>  CMFCMenuButton::SizeToContent

Изменение размера кнопки в соответствии с его размер текста и размер изображения.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Параметры

*bCalcOnly*<br/>
[in] Логический параметр, который указывает, является ли этот метод изменяет размер кнопки.

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объект, который указывает новый размер для кнопки.

### <a name="remarks"></a>Примечания

Если вы вызываете эту функцию и *bCalcOnly* имеет значение TRUE, `SizeToContent` вычислит только новый размер кнопки.

Новый размер кнопки вычисляется в соответствии с текст кнопки, изображения и стрелка. Платформа также добавляет в предварительно определенных полей для 10 точек для горизонтальной края и 5 точек для вертикального края.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)
