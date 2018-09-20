---
title: Класс CMFCRibbonCheckBox | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b10004551a594d6f969ffaf7893cd2e7efe2d76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396562"
---
# <a name="cmfcribboncheckbox-class"></a>Класс CMFCRibbonCheckBox

Класс `CMFCRibbonCheckBox` реализует флажок, который можно добавить на панель ленты, панель быстрого доступа или во всплывающее меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Переопределяет [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Переопределяет [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Переопределяет [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Переопределяет `CMFCRibbonButton::IsDrawTooltipImage`.)|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Переопределяет [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Переопределяет [CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Переопределяет `CMFCRibbonButton::OnDrawOnList`.)|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>Примечания

Чтобы использовать класс `CMFCRibbonCheckBox` в вашем приложении, добавьте в код следующий конструктор:

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```
где *nID* идентификатор команды "флажок" и *lpszText* — текстовая метка флажка.

Типа "флажок" можно добавить на панель ленты с помощью [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncheckbox.h

##  <a name="cmfcribboncheckbox"></a>  CMFCRibbonCheckBox::CMFCRibbonCheckBox

Конструктор объекта флажок ленты

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
[in] Указывает идентификатор команды.

*lpszText*<br/>
[in] Указывает текстовую метку.

### <a name="return-value"></a>Возвращаемое значение

Создает объект "флажок" ленты.

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCRibbonCheckBox` класса.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

##  <a name="getcompactsize"></a>  CMFCRibbonCheckBox::GetCompactSize

При переопределении возвращает компактный размер поля с флажком.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на CDC, связанного с флажком.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CSize` , содержащий компактный размер поля с флажком.

### <a name="remarks"></a>Примечания

Если не переопределен, возвращает промежуточный размер поля с флажком.

##  <a name="getintermediatesize"></a>  CMFCRibbonCheckBox::GetIntermediateSize

Возвращает промежуточный размер поля с флажком.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на CDC, связанные с этот флажок.

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize` объект, содержащий промежуточный размер поля с флажком.

### <a name="remarks"></a>Примечания

Если не переопределен, вычисляет промежуточный размер размер по умолчанию флажок ( `AFX_CHECK_BOX_DEFAULT_SIZE`) плюс размер текста, а также поля.

##  <a name="getregularsize"></a>  CMFCRibbonCheckBox::GetRegularSize

Возвращает стандартный размер поля с флажком.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на объект CDC, связанный с этот флажок.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CSize` , содержащий стандартный размер поля с флажком.

### <a name="remarks"></a>Примечания

Если не переопределен, возвращает промежуточный размер поля с флажком.

##  <a name="isdrawtooltipimage"></a>  CMFCRibbonCheckBox::IsDrawTooltipImage

Указывает, есть ли подсказки изображения, связанного с флажком.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если есть изображение всплывающей подсказки, связанный с флажком, или FALSE, если это не так.

### <a name="remarks"></a>Примечания

##  <a name="ondraw"></a>  CMFCRibbonCheckBox::OnDraw

Вызывается платформой для отрисовки флажка, используя задаваемые значения контекста устройства.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на CDC, в котором отображается флажок.

### <a name="remarks"></a>Примечания

##  <a name="ondrawmenuimage"></a>  CMFCRibbonCheckBox::OnDrawMenuImage

Вызывается платформой для отрисовки меню изображений для флажка.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Параметры

[in] *CDC** указатель на CDC, связанного с флажком.

*CRect*<br/>
[in] Объект `CRect` объект, указывающий прямоугольник, в котором должно быть нарисовано изображение меню.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если для рисования изображения, или значение FALSE, если это не так.

### <a name="remarks"></a>Примечания

Если не переопределен, возвращает значение FALSE.

##  <a name="ondrawonlist"></a>  CMFCRibbonCheckBox::OnDrawOnList

Вызывается платформой для отрисовки флажка в поле со списком команд.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства, в котором отображается флажок.

*strText*<br/>
[in] Отображаемый текст.

*nTextOffset*<br/>
[in] Расстояние в пикселях от левого края поле со списком для отображения текста.

*Rect*<br/>
[in] Прямоугольник отображения для флажка.

*bIsSelected*<br/>
[in] Значение TRUE, если флажок выбранных, или FALSE, если это не так.

*bHighlighted*<br/>
[in] Значение TRUE, если флажок имеет выделенный, или FALSE, если это не так.

### <a name="remarks"></a>Примечания

##  <a name="setaccdata"></a>  CMFCRibbonCheckBox::SetACCData

Задает данные специальных возможностей для флажка.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pParent*<br/>
Родительское окно поля с флажком.

*data*<br/>
Данные специальных возможностей для флажка.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод задает данные специальных возможностей для флажка и всегда возвращает значение TRUE. Переопределите этот метод, чтобы задать данные специальных возможностей и возвращать значение, указывающее на успешное или неуспешное выполнение.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)
