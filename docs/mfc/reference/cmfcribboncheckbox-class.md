---
title: Класс Кмфкриббончеккбокс
ms.date: 11/04/2016
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
ms.openlocfilehash: a8048f860a2cce75c37a065cfdd2751141054f1b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446244"
---
# <a name="cmfcribboncheckbox-class"></a>Класс Кмфкриббончеккбокс

Класс `CMFCRibbonCheckBox` реализует флажок, который можно добавить на панель ленты, панель быстрого доступа или во всплывающее меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кмфкриббончеккбокс:: Кмфкриббончеккбокс](#cmfcribboncheckbox)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кмфкриббончеккбокс:: Жеткомпактсизе](#getcompactsize)|(Переопределяет [CMFCRibbonButton:: жеткомпактсизе](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[Кмфкриббончеккбокс:: GetIntermediateSize](#getintermediatesize)|(Переопределяет [CMFCRibbonButton:: GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[Кмфкриббончеккбокс:: Жетрегуларсизе](#getregularsize)|(Переопределяет [CMFCRibbonButton:: жетрегуларсизе](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[Кмфкриббончеккбокс:: Исдравтултипимаже](#isdrawtooltipimage)|(Переопределяет `CMFCRibbonButton::IsDrawTooltipImage`.)|
|[Кмфкриббончеккбокс:: OnDraw](#ondraw)|(Переопределяет [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[Кмфкриббончеккбокс:: Ондравменуимаже](#ondrawmenuimage)|(Переопределяет [метод CMFCRibbonBaseElement:: ондравменуимаже](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[Кмфкриббончеккбокс:: Ондравонлист](#ondrawonlist)|(Переопределяет `CMFCRibbonButton::OnDrawOnList`.)|
|[Кмфкриббончеккбокс:: Сетаккдата](#setaccdata)|(Переопределяет [CMFCRibbonButton:: сетаккдата](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>Remarks

Чтобы использовать класс `CMFCRibbonCheckBox` в вашем приложении, добавьте в код следующий конструктор:

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

где *NID* — это идентификатор команды для флажка, а *лпсзтекст* — текстовая метка флажка.

Флажок можно добавить на панель ленты с помощью [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[кмфкриббончеккбокс](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксриббончеккбокс. h

##  <a name="cmfcribboncheckbox"></a>Кмфкриббончеккбокс:: Кмфкриббончеккбокс

Конструктор объекта флажка ленты

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
окне Указывает идентификатор команды.

*lpszText*<br/>
окне Задает текстовую метку.

### <a name="return-value"></a>Возвращаемое значение

Конструирует объект флажка ленты.

### <a name="example"></a>Пример

В следующем примере показано, как создать объект класса `CMFCRibbonCheckBox`.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

##  <a name="getcompactsize"></a>Кмфкриббончеккбокс:: Жеткомпактсизе

При переопределении возвращает размер компактного флажка.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на CDC, связанный с флажком.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект `CSize`, который содержит компактный размер флажка.

### <a name="remarks"></a>Remarks

Если значение не переопределено, Возвращает промежуточный размер флажка.

##  <a name="getintermediatesize"></a>Кмфкриббончеккбокс:: GetIntermediateSize

Возвращает промежуточный размер флажка.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на CDC, связанный с этим флажком.

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize`, содержащий промежуточный размер флажка.

### <a name="remarks"></a>Remarks

Если не переопределен, вычисляет промежуточный размер как размер флажка по умолчанию (`AFX_CHECK_BOX_DEFAULT_SIZE`), а также размер текста и поля.

##  <a name="getregularsize"></a>Кмфкриббончеккбокс:: Жетрегуларсизе

Возвращает обычный размер флажка.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на объект CDC, связанный с этим флажком.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект `CSize`, который содержит обычный размер флажка.

### <a name="remarks"></a>Remarks

Если значение не переопределено, Возвращает промежуточный размер флажка.

##  <a name="isdrawtooltipimage"></a>Кмфкриббончеккбокс:: Исдравтултипимаже

Указывает, имеется ли изображение подсказки, связанное с флажком.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если имеется изображение подсказки, связанное с флажком, или значение FALSE в противном случае.

### <a name="remarks"></a>Remarks

##  <a name="ondraw"></a>Кмфкриббончеккбокс:: OnDraw

Вызывается платформой для отрисовки флажка с помощью указанного контекста устройства.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на объект CDC, в котором должен быть размещен флажок.

### <a name="remarks"></a>Remarks

##  <a name="ondrawmenuimage"></a>Кмфкриббончеккбокс:: Ондравменуимаже

Вызвано структурой для рисования изображения меню для флажка.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Параметры

окне *CDC&#42;*<br/>
Указатель на CDC, связанный с флажком.

*крект*<br/>
окне Объект `CRect`, указывающий прямоугольник, в котором следует нарисовать изображение меню.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если изображение было нарисован, или значение FALSE в противном случае.

### <a name="remarks"></a>Remarks

Если не переопределен, возвращает значение FALSE.

##  <a name="ondrawonlist"></a>Кмфкриббончеккбокс:: Ондравонлист

Вызывается платформой для отображения флажка в списке команд.

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

*pDC*<br/>
окне Указатель на контекст устройства, в котором должен быть размещен флажок.

*стртекст*<br/>
[in] Отображаемый текст.

*нтекстоффсет*<br/>
окне Расстояние (в пикселях) от левого края окна списка до отображаемого текста.

*rect*<br/>
окне Отображаемый прямоугольник для флажка.

*бисселектед*<br/>
окне Значение TRUE, если флажок установлен, или значение FALSE в противном случае.

*бхигхлигхтед*<br/>
окне Значение TRUE, если флажок выделен, или FALSE в противном случае.

### <a name="remarks"></a>Remarks

##  <a name="setaccdata"></a>Кмфкриббончеккбокс:: Сетаккдата

Задает данные специальных возможностей для флажка.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*ппарент*<br/>
Родительское окно флажка.

*data*<br/>
Данные специальных возможностей для флажка.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Remarks

По умолчанию этот метод устанавливает данные специальных возможностей для флажка и всегда возвращает значение TRUE. Переопределите этот метод, чтобы задать данные специальных возможностей и возвращать значение, указывающее на успешное или неуспешное выполнение.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)
