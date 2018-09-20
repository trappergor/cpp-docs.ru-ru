---
title: Класс CMFCRibbonLabel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d54662663e2b3223f4122eae93327b9a05337b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382236"
---
# <a name="cmfcribbonlabel-class"></a>Класс CMFCRibbonLabel

Реализует недоступную для щелчка текстовую метку для ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Создает и инициализирует `CMFCRibbonLabel` объект с указанной текстовой строки.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonLabel::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Определяет, какие данные специальных возможностей для текущего элемента метка ленты. (Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>Примечания

После создания метка на ленте, добавьте его на панель, вызвав [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

Невозможно добавить метку ленты, панель быстрого доступа.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonLabel.h

##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel

Создает и инициализирует [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) объекта, который отображает заданную текстовую строку.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
[in] Текст, появляющийся в метке.

*bIsMultiLine*<br/>
[in] Значение TRUE, чтобы указать, что метка Многострочная метка; в противном случае — значение FALSE.

##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData

Определяет, какие данные специальных возможностей для текущего элемента метка ленты.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pParent*<br/>
[in] Представляет родительское окно метку ленты.

*data*<br/>
[out] Объект типа `CAccessibilityData` заполняется данные специальных возможностей текущей метки ленты.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *данных* параметр был успешно заполнен данные специальных возможностей текущей метки ленты; в противном случае — значение FALSE.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
