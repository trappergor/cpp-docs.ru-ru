---
title: Класс CMFCColorPickerCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28085c49903aff1c49fa9114b6a0828c5493840b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077924"
---
# <a name="cmfccolorpickerctrl-class"></a>Класс CMFCColorPickerCtrl

`CMFCColorPickerCtrl` Класс предоставляет функциональные возможности для элемента управления, который используется для выбора цветов.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Создает объект `CMFCColorPickerCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Получает цвет, выбранного пользователем.|
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Извлекает значения оттенка, освещенности и насыщенность цвета, выбранного пользователем.|
|[CMFCColorPickerCtrl::GetHue](#gethue)|Возвращает компонент оттенок цвета, выбранного пользователем.|
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Возвращает компонент освещенности, цвета, выбранного пользователем.|
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Возвращает компонент насыщенность цвета, выбранного пользователем.|
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Задает текущий цвет цвет, определяемый указанных компонентов цвета RGB или шестиугольник указанной ячейки.|
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Задает текущий цвет указанное значение цвета RGB.|
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Задает текущий цвет указанное значение цвета HLS.|
|[CMFCColorPickerCtrl::SetHue](#sethue)|Изменяет компонента оттенка выбранного цвета.|
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Изменяет компонент освещенности выбранный цвет.|
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Задает ширину панели освещенности в средстве выбора цвета.|
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Задает начальное выбранного цвета.|
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Задает текущую цветовую палитру.|
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Изменяет компонента насыщенности выбранного цвета.|
|[CMFCColorPickerCtrl::SetType](#settype)|Задает тип элемента управления выбора цвета для отображения.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Вызвано структурой перед отображением курсор, указывающий на выбранный цвет.|

## <a name="remarks"></a>Примечания

Стандартные цвета выбираются из палитры цветов шестиугольник, а также пользовательские цвета выбираются из панели освещенности там, где цвета задаются с помощью красного, зеленого и синего нотацию или нотацию hue/satuaration/освещенности.

На следующем рисунке показано несколько `CMFCColorPickerCtrl` объектов.

![Диалоговое окно для CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "colorpicker")

`CMFCColorPickerCtrl` Поддерживает две пары стили. Стили ШЕСТНАДЦАТЕРИЧНЫЕ и HEX_GREYSCALE подходят для стандартный цвет выделения. Средство ВЫБОРА и ЯРКОСТЬЮ стили подходят для выбора пользовательский цвет.

Выполните следующие действия для включения `CMFCColorPickerCtrl` элемента управления в диалоговое окно:

1. Если вы используете **ClassWizard**, вставьте новый элемент управления button в ваш шаблон диалогового окна (поскольку `CMFCColorPickerCtrl` класс, наследуемый от `CButton` класса).

1. Вставьте переменную-член, которая связана с новый элемент управления button в классе диалогового окна. Затем измените тип переменной из `CButton` для `CMFCColorPickerCtrl`.

1. Вставить `WM_INITDIALOG` обработчик сообщений для класса диалогового окна. В обработчике задайте тип, палитры и начальной выбранный цвет `CMFCColorPickerCtrl` элемента управления.

## <a name="example"></a>Пример

Следующий пример демонстрирует настройку `CMFCColorPickerCtrl` объекта с помощью различных методов в `CMFCColorPickerCtrl` класса. В примере показано, как задать тип элемента управления выбора и как задать цвет, hue, освещенности и насыщенность. Пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcolorpickerctrl.h

##  <a name="cmfccolorpickerctrl"></a>  CMFCColorPickerCtrl::CMFCColorPickerCtrl

Создает объект `CMFCColorPickerCtrl`.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="drawcursor"></a>  CMFCColorPickerCtrl::DrawCursor

Вызвано структурой перед отображением курсор, указывающий на выбранный цвет.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*Rect*<br/>
[in] Задает прямоугольную область вокруг выбранного цвета.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если вам нужно изменить форму курсор, который указывает на выбранный цвет.

##  <a name="getcolor"></a>  CMFCColorPickerCtrl::GetColor

Получает цвет, выбранного пользователем.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение выбранного цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="gethls"></a>  CMFCColorPickerCtrl::GetHLS

Извлекает значения оттенка, освещенности и насыщенность цвета, выбранного пользователем.

```
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>Параметры

*Hue*<br/>
[out] Указатель на переменную типа double, получающий hue сведения.

*освещенность*<br/>
[out] Указатель на переменную типа double, получающий сведения освещенности.

*насыщенность*<br/>
[out] Указатель на переменную типа double, получающий насыщенность сведения.

### <a name="remarks"></a>Примечания

##  <a name="gethue"></a>  CMFCColorPickerCtrl::GetHue

Возвращает компонент оттенок цвета, выбранного пользователем.

```
double GetHue() const;
```

### <a name="return-value"></a>Возвращаемое значение

Компонент оттенка выбранного цвета.

### <a name="remarks"></a>Примечания

##  <a name="getluminance"></a>  CMFCColorPickerCtrl::GetLuminance

Возвращает компонент освещенности, цвета, выбранного пользователем.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Возвращаемое значение

Компонент освещенности выбранного цвета.

### <a name="remarks"></a>Примечания

##  <a name="getsaturation"></a>  CMFCColorPickerCtrl::GetSaturation

Получает значение насыщенности цвета, выбранного пользователем.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Возвращаемое значение

Компонент насыщенности выбранного цвета.

### <a name="remarks"></a>Примечания

##  <a name="selectcellhexagon"></a>  CMFCColorPickerCtrl::SelectCellHexagon

Задает текущий цвет цвет, определяемый указанных компонентов цвета RGB или шестиугольник указанной ячейки.

```
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>Параметры

*R*<br/>
[in] Компонент красного цвета.

*G*<br/>
[in] Компонент зеленого цвета.

*B*<br/>
[in] Компонент синего цвета.

*x*<br/>
[in] Координата по оси x курсор, который указывает на шестиугольник ячейки.

*y*<br/>
[in] Координата по оси y курсор, который указывает на шестиугольник ячейки.

### <a name="return-value"></a>Возвращаемое значение

Вторая перегрузка этого метода всегда возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Первая перегрузка этого метода задает текущий цвет, цвет, соответствующий элемент управления для выбора цвета, заданного компонентам красного, зеленого и синего цветов.

Вторая перегрузка этого метода задает текущий цвет цвету ячейки шестиугольник, которое указывает, с позиции указанного курсора.

##  <a name="setcolor"></a>  CMFCColorPickerCtrl::SetColor

Задает текущий цвет указанное значение цвета RGB.

```
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
[in] Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="sethls"></a>  CMFCColorPickerCtrl::SetHLS

Задает текущий цвет указанное значение цвета HLS.

```
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>Параметры

*Hue*<br/>
[in] Значение оттенка.

*освещенность*<br/>
[in] Значение освещенности.

*насыщенность*<br/>
[in] Значение насыщенности.

*bInvalidate*<br/>
[in] Значение TRUE, чтобы принудительно окно для немедленного обновления на новый цвет; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

##  <a name="sethue"></a>  CMFCColorPickerCtrl::SetHue

Изменяет оттенка выбранного цвета.

```
void SetHue(double Hue);
```

### <a name="parameters"></a>Параметры

*Hue*<br/>
[in] Значение оттенка.

### <a name="remarks"></a>Примечания

##  <a name="setluminance"></a>  CMFCColorPickerCtrl::SetLuminance

Изменяет яркостью выбранный цвет.

```
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>Параметры

*Освещенность*<br/>
[in] Значение освещенности.

### <a name="remarks"></a>Примечания

##  <a name="setluminancebarwidth"></a>  CMFCColorPickerCtrl::SetLuminanceBarWidth

Задает ширину панели освещенности в средстве выбора цвета.

```
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>Параметры

*w*<br/>
[in] Ширина панели освещенности измеряется в пикселях.

### <a name="remarks"></a>Примечания

Используйте этот метод для изменения размера панели освещенности, которая находится на **Custom** вкладку элемента управления выбора цвета. *w* параметр задает новую ширину панели освещенности. Значение ширины учитывается, если оно превышает три четверти Ширина клиентской области.

##  <a name="setoriginalcolor"></a>  CMFCColorPickerCtrl::SetOriginalColor

Задает начальное выбранного цвета.

```
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>Параметры

*ref*<br/>
[in] Значение цвета RGB.

### <a name="remarks"></a>Примечания

Этот метод вызывается при инициализации управление палитрой.

##  <a name="setpalette"></a>  CMFCColorPickerCtrl::SetPalette

Задает текущую цветовую палитру.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*pPalette*<br/>
[in] Указатель на цветовую палитру.

### <a name="remarks"></a>Примечания

Цветовая палитра определяет массив цветов, представленные в средстве выбора цвета.

##  <a name="setsaturation"></a>  CMFCColorPickerCtrl::SetSaturation

Изменяет насыщенности выбранного цвета.

```
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>Параметры

*насыщенность*<br/>
[in] Значение насыщенности.

### <a name="remarks"></a>Примечания

##  <a name="settype"></a>  CMFCColorPickerCtrl::SetType

Задает тип элемента управления выбора цвета для отображения.

```
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>Параметры

*colorType*<br/>
[in] Тип элемента управления средства выбора цвета.

Типы определяются `CMFCColorPickerCtrl::COLORTYPE` перечисления. Возможные типы являются ОСВЕЩЕННОСТИ "," Выбор "," HEX "и" HEX_GREYSCALE. По умолчанию используется тип ВЫБОРА.

### <a name="remarks"></a>Примечания

Чтобы указать тип элемента управления средства выбора цвета, этот метод вызывается до создания элемента управления Windows.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)
