---
title: Класс CMFCMenuButton
ms.date: 07/15/2019
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
- AFXMENUBUTTON/CMFCMenuButton::m_bDefaultClick
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
- CMFCMenuButton [MFC], m_bDefaultClick
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: d7c23cbda0a5af4dc3fa6b2d9f59497acc9bf5ff
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505211"
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
|[CMFCMenuButton:: CMFCMenuButton](#cmfcmenubutton)|Создает объект `CMFCMenuButton`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCMenuButton::P Ретранслатемессаже](#pretranslatemessage)|Вызывается платформой для преобразования оконных сообщений до их отправки. (Переопределяет `CMFCButton::PreTranslateMessage`.)|
|[CMFCMenuButton:: SizeToContent](#sizetocontent)|Изменяет размер кнопки в соответствии с ее размером текста и изображения.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCMenuButton:: m_bOSMenu](#m_bosmenu)|Указывает, следует ли отображать системное всплывающее меню по умолчанию или использовать [кконтекстменуманажер:: метод TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|
|[CMFCMenuButton:: m_bRightArrow](#m_brightarrow)|Указывает, отображается ли всплывающее меню под кнопкой или справа от нее.|
|[CMFCMenuButton:: m_bStayPressed](#m_bstaypressed)|Указывает, изменяет ли кнопка меню свое состояние после того, как пользователь отпускает кнопку.|
|[CMFCMenuButton:: m_hMenu](#m_hmenu)|Маркер для присоединенного меню Windows.|
|[CMFCMenuButton:: m_nMenuResult](#m_nmenuresult)|Идентификатор, указывающий, какой элемент пользователь выбрал во всплывающем меню.|
|[CMFCMenuButton:: m_bDefaultClick](#m_bdefaultclick)| Разрешить обработку по умолчанию (с текстом или изображением кнопки).|

## <a name="remarks"></a>Примечания

Класс является производным от [класса кмфкбуттон](../../mfc/reference/cmfcbutton-class.md) , который, в свою очередь, является производным от [класса кбуттон.](../../mfc/reference/cbutton-class.md) `CMFCMenuButton` Таким образом, вы можете `CMFCMenuButton` использовать в коде так же, как и при `CButton`использовании.

При создании `CMFCMenuButton`необходимо передать маркер связанному всплывающему меню. Затем вызовите функцию `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent`проверяет, достаточно ли размера кнопки для включения стрелки, указывающей на расположение всплывающего окна под кнопкой или справа от нее.

## <a name="example"></a>Пример

В следующем примере показано, как задать маркер меню, присоединенного к кнопке, изменить размер кнопки в соответствии с размером текста и изображения, а также задать всплывающее меню, отображаемое платформой. Этот фрагмент кода является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[кмфкбуттон](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксменубуттон. h

##  <a name="cmfcmenubutton"></a>CMFCMenuButton:: CMFCMenuButton

Конструирует новый объект [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) .

```
CMFCMenuButton();
```

##  <a name="m_bosmenu"></a>CMFCMenuButton:: m_bOSMenu

Логическая переменная-член, которая указывает, какое всплывающее меню отображается платформой.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Примечания

Если `m_bOSMenu` имеет значение true, платформа вызывает наследуемый `TrackPopupMenu` метод для этого объекта. В противном случае платформа вызывает [кконтекстменуманажер:: метод TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).

##  <a name="m_brightarrow"></a>CMFCMenuButton:: m_bRightArrow

Логическая переменная-член, которая указывает расположение всплывающего меню.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Примечания

Когда пользователь нажимает кнопку меню, приложение отображает всплывающее меню. Платформа отобразит всплывающее меню под кнопкой или справа от кнопки. Кнопка также имеет маленькую стрелку, которая указывает, где появится всплывающее меню. Если `m_bRightArrow` имеет значение true, платформа отображает всплывающее меню справа от кнопки. В противном случае отображается всплывающее меню под кнопкой.

##  <a name="m_bstaypressed"></a>CMFCMenuButton:: m_bStayPressed

Логическая переменная-член, которая указывает, отображается ли кнопка меню во время выбора пользователем во всплывающем меню.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Примечания

`m_bStayPressed` Если элемент имеет значение false, кнопка меню не будет нажата, когда компонент использует нажатие кнопки. В этом случае платформа отображает только всплывающее меню.

`m_bStayPressed` Если элемент имеет значение true, кнопка меню становится нажатой, когда пользователь нажимает кнопку. Она остается нажатой до тех пор, пока пользователь не закроет всплывающее меню, выполнив выбор или отменив.

##  <a name="m_hmenu"></a>CMFCMenuButton:: m_hMenu

Маркер присоединенного меню.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Примечания

Платформа отображает меню, обозначенное этой переменной члена, когда пользователь нажимает кнопку меню.

##  <a name="m_nmenuresult"></a>CMFCMenuButton:: m_nMenuResult

Целое число, указывающее, какой элемент пользователь выбирает во всплывающем меню.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Примечания

Значение этой переменной-члена равно нулю, если пользователь отменяет меню, не выполняя выбор или при возникновении ошибки.

##  <a name="m_bdefaultclick"></a>CMFCMenuButton:: m_bDefaultClick

Разрешает обработку текста или изображений на кнопке по умолчанию.

```
BOOL  m_bDefaultClick;
```

### <a name="remarks"></a>Примечания

Установка значения false для m_bDefaultClick приводит к тому, что при нажатии кнопки в любом месте на кнопке отображается меню.

##  <a name="m_nmenuresult"></a>CMFCMenuButton:: m_nMenuResult

Целое число, указывающее, какой элемент пользователь выбирает во всплывающем меню.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Примечания

##  <a name="pretranslatemessage"></a>CMFCMenuButton::P Ретранслатемессаже

Вызывается платформой для преобразования оконных сообщений до их отправки.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*пмсг*<br/>
окне Указывает на структуру [MSG](/windows/win32/api/winuser/ns-winuser-msg) , содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение было переведено и не должно быть отправлено. 0, если сообщение не было переведено и должно быть отправлено.

### <a name="remarks"></a>Примечания

##  <a name="sizetocontent"></a>CMFCMenuButton:: SizeToContent

Изменяет размер кнопки в зависимости от размера текста и размера изображения.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Параметры

*бкалконли*<br/>
окне Логический параметр, указывающий, изменяет ли этот метод кнопку.

### <a name="return-value"></a>Возвращаемое значение

Объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) , указывающий новый размер кнопки.

### <a name="remarks"></a>Примечания

Если вызвать эту функцию, а *бкалконли* — true, `SizeToContent` будет вычислять только новый размер кнопки.

Новый размер кнопки вычисляется в соответствии с текстом кнопки, изображением и стрелкой. Платформа также добавляет предварительно определенные поля с 10 пикселями для горизонтального края и 5 пикселей для вертикального края.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)
