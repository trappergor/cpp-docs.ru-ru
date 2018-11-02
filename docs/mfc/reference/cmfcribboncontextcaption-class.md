---
title: Класс CMFCRibbonContextCaption
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: 3e6d8dcd643a58b3df60488b50da08288a34bab9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628388"
---
# <a name="cmfcribboncontextcaption-class"></a>Класс CMFCRibbonContextCaption

Реализует цветной заголовок, который отображается в верхней части категории "лента" или категории "контекст".

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Возвращает цвет заголовка.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|

## <a name="remarks"></a>Примечания

Создать экземпляр этого класса напрямую невозможно. [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) класс внутренне использует этот класс для добавления цвета категориям ленты.

Чтобы задать цвет категорий ленты, вызовите [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Чтобы задать цвет для категорий контекста, вызовите [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonBar.h

##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor

Возвращает цвет фона заголовка.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение может быть одно из следующих значений:

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>Примечания

Цвет заголовка можно задать путем вызова [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) или [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX

Получает положение правой границы данной категории вкладки ленты.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает справа X-значение для охватывающего прямоугольника `CMFCRibbonCategory` вкладку ленты объекта или значение -1, если вкладки усекается.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[Класс CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
