---
title: Класс CMFCLinkCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: a4324fad7668907600cbaebeb5c9de4ad0e7c1e4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302728"
---
# <a name="cmfclinkctrl-class"></a>Класс CMFCLinkCtrl

`CMFCLinkCtrl` Класс отображает кнопку в виде гиперссылки и вызывает целевой объект связи, при нажатии кнопки.

## <a name="syntax"></a>Синтаксис

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCLinkCtrl::SetURL](#seturl)|Отображает указанный URL-адрес в виде текста кнопки.|
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Задает неявный протокол (например, «http:») URL-адреса.|
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Изменяет размер кнопку, чтобы содержать текст кнопки или точечного рисунка.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Вызвано структурой перед началом рисования прямоугольника фокуса кнопки.|

## <a name="remarks"></a>Примечания

После нажатия кнопки, который является производным от `CMFCLinkCtrl` класс, платформа передает URL-адрес кнопки в качестве параметра `ShellExecute` метод. Затем `ShellExecute` метод открывает целевой URL-адреса.

## <a name="example"></a>Пример

В следующем примере показано, как задать размер `CMFCLinkCtrl` , а также для задания URL-адрес и всплывающей подсказки в `CMFCLinkCtrl` объекта. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxlinkctrl.h

##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect

Вызвано структурой перед началом рисования прямоугольника фокуса кнопки.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rectClient*<br/>
[in] Ограничивающий прямоугольник для этого элемента управления ссылки.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если вы хотите использовать собственный код для рисования прямоугольника фокуса кнопки.

##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL

Отображает указанный URL-адрес в виде текста кнопки.

```
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
[in] Текст кнопки для отображения.

### <a name="remarks"></a>Примечания

##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix

Задает неявный протокол (например, «http:») URL-адреса.

```
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Параметры

*lpszPrefix*<br/>
[in] Префикс URL-адрес протокола.

### <a name="remarks"></a>Примечания

Этот метод позволяет задать префикс URL-адреса. Префикс не отображается на кнопке, но его можно использовать для перейдите к целевой URL-адрес.

##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent

Изменяет размер кнопку, чтобы содержать текст кнопки или точечного рисунка.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Параметры

*bVCenter*<br/>
[in] Значение TRUE, чтобы центрировать текст и кнопки растрового изображения по вертикали между верхней и нижней части элемента управления ссылки; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

*bHCenter*<br/>
[in] Значение TRUE, чтобы центрировать текст и кнопки растрового изображения по горизонтали между левой и правой стороны элемента управления ссылки; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий новый размер элемента управления ссылки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CLinkCtrl](../../mfc/reference/clinkctrl-class.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)
