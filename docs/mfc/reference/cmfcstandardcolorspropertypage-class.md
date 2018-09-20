---
title: Класс CMFCStandardColorsPropertyPage | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 475780db8883fe9a8c8393648876764406cee376
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380598"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>Класс CMFCStandardColorsPropertyPage

Представляет страницу свойств, в котором пользователям выбирать стандартные цвета в диалоговом окне цвет.

## <a name="syntax"></a>Синтаксис

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|`CMFCStandardColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCStandardColorsPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|

### <a name="remarks"></a>Примечания

`CMFCColorDialog` Использует этот класс для отображения страницы свойств стандартный цвет. Дополнительные сведения о `CMFCColorDialog`, см. в разделе [класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxstandardcolorspropertypage.h

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)<br/>
[Класс CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
