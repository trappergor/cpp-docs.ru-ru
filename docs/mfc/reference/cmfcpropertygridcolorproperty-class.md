---
title: Класс CMFCPropertyGridColorProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 65c2c22c93dc3acb50fc4627c3710a3f0c86aeb0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303967"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>Класс CMFCPropertyGridColorProperty

Класс `CMFCPropertyGridColorProperty` поддерживает элемент управления списка свойств, открывающий диалоговое окно выбора цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Создает объект `CMFCPropertyGridColorProperty`.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Позволяет *автоматического* кнопку в диалоговом окне выбора цвета. (Метка стандартной кнопки автоматического выбора **автоматического**.)|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Позволяет *других* кнопку в диалоговом окне выбора цвета. (Стандартной меткой другая кнопка **Дополнительные цвета**.)|
|`CMFCPropertyGridColorProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Возвращает текущий цвет свойства.|
|`CMFCPropertyGridColorProperty::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|`CMFCPropertyGridColorProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|Вызывается платформой для отображения значения свойства. (Переопределяет [CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|
|`CMFCPropertyGridColorProperty::OnEdit`|Вызывается платформой непосредственно перед изменением значения свойства пользователем. (Переопределяет [CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Вызывается платформой при присвоении изменяемому свойству нового значения. (Переопределяет [CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Задает новый цвет свойства.|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов в текущей таблице свойств цвета.|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Задает изменяемому свойству изначальное значение.|

## <a name="remarks"></a>Примечания

Класс `CMFCPropertyGridColorProperty` поддерживает свойство цвета, которое можно добавить в элемент управления "список свойств". Дополнительные сведения см. в разделе [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется создание объекта класса `CMFCPropertyGridColorProperty` и его настройка с помощью различных методов класса `CMFCPropertyGridColorProperty`. В коде показывается, как можно задействовать кнопки автоматического выбора и выбора другого цвета, а также выполняется назначение цвета и количества столбцов. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridcolorproperty"></a>  CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty

Создает объект `CMFCPropertyGridColorProperty`.

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>Параметры

*strName*<br/>
[in] Имя свойства.

*color*<br/>
[in] Значение цвета свойства.

*pPalette*<br/>
[in] Указатель на палитру цветов. Значение по умолчанию имеет значение NULL.

*lpszDescr*<br/>
[in] Описание свойства. Значение по умолчанию имеет значение NULL.

*dwData*<br/>
[in] Данные приложения, такие как целое число или указатель с другими данными, который связан со свойством. Значение по умолчанию — 0.

##  <a name="enableautomaticbutton"></a>  CMFCPropertyGridColorProperty::EnableAutomaticButton

Позволяет *автоматического* кнопку в диалоговом окне выбора цвета. (Метка стандартной кнопки автоматического выбора **автоматического**.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Текст метки автоматической кнопки.

*colorAutomatic*<br/>
[in] Значение цвета RGB цвета автоматически (по умолчанию).

*bEnable*<br/>
[in] Значение TRUE для включения автоматической кнопки; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

##  <a name="enableotherbutton"></a>  CMFCPropertyGridColorProperty::EnableOtherButton

Позволяет *других* кнопку в диалоговом окне выбора цвета. (Стандартной меткой другая кнопка **Дополнительные цвета**.)

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Текст метки другие кнопки.

*bAltColorDlg*<br/>
[in] True, если `CMFCColorDialog` диалоговом окне; Значение FALSE, чтобы отобразить диалоговое окно выбора стандартный цвет. Значение по умолчанию — TRUE.

*bEnable*<br/>
[in] Значение TRUE для отображения кнопки; в противном случае — значение FALSE.  Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

##  <a name="getcolor"></a>  CMFCPropertyGridColorProperty::GetColor

Возвращает текущий цвет свойства.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="setcolor"></a>  CMFCPropertyGridColorProperty::SetColor

Задает новый цвет свойства.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="setcolumnsnumber"></a>  CMFCPropertyGridColorProperty::SetColumnsNumber

Задает число столбцов в текущей таблице свойств цвета.

```
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>Параметры

*nColumnsNumber*<br/>
[in] Предпочтительный количество столбцов в таблице свойств цвета.

### <a name="remarks"></a>Примечания

Этот метод задает значение `m_nColumnsNumber` защищенный элемент данных.

##  <a name="setoriginalvalue"></a>  CMFCPropertyGridColorProperty::SetOriginalValue

Задает изменяемому свойству изначальное значение.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*varValue*<br/>
[in] Значение.

### <a name="remarks"></a>Примечания

Используйте [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) метод, чтобы восстановить исходное значение измененного свойства.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
