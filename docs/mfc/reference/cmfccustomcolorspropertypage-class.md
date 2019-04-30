---
title: Класс CMFCCustomColorsPropertyPage
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: b28711991835dd14929e5387709046c3867c715e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403702"
---
# <a name="cmfccustomcolorspropertypage-class"></a>Класс CMFCCustomColorsPropertyPage

Представляет страницу свойств, можно выбрать цвет в диалоговом окне цвет.

## <a name="syntax"></a>Синтаксис

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|name|Описание|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|name|Описание|
|`CMFCCustomColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Задает компоненты цвет страницы свойств.|

### <a name="remarks"></a>Примечания

`CMFCColorDialog` Использует этот класс для отображения страницы свойств пользовательского цвета. Дополнительные сведения о `CMFCColorDialog`, см. в разделе [класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется создание `CMFCCustomColorsPropertyPage` и задайте компонентов цвета страницы свойств.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcustomcolorspropertypage.h

##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup

Задает компоненты цвет страницы свойств.

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
|*R*|[in] Красный компонент RGB-значение.|
|*G*|[in] Зеленый компонент RGB-значение.|
|*B*|[in] Синий компонент RGB-значение.|

### <a name="remarks"></a>Примечания

Этот метод обновляет текущий RGB и связанные HLS (hue, освещенность и насыщенность) цвет значения страницы свойств. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) метод вызывает этот метод, когда платформа инициализирует диалоговое окно «цвет» или нажатии левой кнопки мыши. Дополнительные сведения о `CMFCColorDialog`, см. в разделе [класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)<br/>
[Класс CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
