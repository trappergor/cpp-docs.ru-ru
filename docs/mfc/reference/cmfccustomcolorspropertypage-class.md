---
title: CMFCCustomColorsPropertyPropertyPage Класс
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: 01b73f44fcf26a820e43eb87a65e99c2ec186e64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367661"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPropertyPage Класс

Представляет страницу свойств, которая может выбрать пользовательские цвета в цветном диалоговом поле.

## <a name="syntax"></a>Синтаксис

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|`CMFCCustomColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCCustomColorsPropertyPropertyPage::Setup](#setup)|Устанавливает цветовые компоненты страницы свойств.|

### <a name="remarks"></a>Remarks

Класс `CMFCColorDialog` использует этот класс для отображения пользовательской страницы свойств цвета. Для получения `CMFCColorDialog`дополнительной информации о, см. [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>Пример

В следующем примере показано, `CMFCCustomColorsPropertyPage` как построить объект и установить цветовые компоненты страницы свойства.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcustomcolorspropertypage.h

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>CMFCCustomColorsPropertyPropertyPage::Setup

Устанавливает цветовые компоненты страницы свойств.

```
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*R*|(в) Красный компонент значения RGB.|
|*Г*|(в) Зеленый компонент значения RGB.|
|*B*|(в) Синий компонент значения RGB.|

### <a name="remarks"></a>Remarks

Этот метод обновляет текущие значения RGB и связанных с ним HLS (оттенк, легкость и насыщенность) цветовые значения страницы свойства. [Метод CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) называет этот метод, когда фреймворк инициализирует цветной диалоговую коробку или пользователь нажимает на левую кнопку мыши. Для получения `CMFCColorDialog`дополнительной информации о, см. [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CmFCStandardColorsPropertyPropertyКласса Класс](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
