---
title: Класс для CMFCColorPickerCtrl | Документы Microsoft
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
ms.openlocfilehash: ad7e67cc32621fc30108767493c3a7bffd481b68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccolorpickerctrl-class"></a>Класс для CMFCColorPickerCtrl
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
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Извлечение значений цветового тона, яркости и насыщенности цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Возвращает компонент оттенок цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Возвращает компонент яркости цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Возвращает компонент насыщенность цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Задает текущий цвет цвет определяется указанным компонентов цвета RGB или шестиугольник указанной ячейки.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Задает текущий цвет указанное значение цвета RGB.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Задает текущий цвет с указанным значением цвета HLS.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Изменяет компонента оттенка выбранного цвета.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Изменяет компонент яркости выбранный цвет.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Задает ширину линейки яркости в средстве выбора цвета.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Задает начальный выбранного цвета.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Задает текущую палитру цветов.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Изменяет компонент насыщенности выбранного цвета.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Задает тип элемента управления выбора цвета для отображения.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Вызывается платформой перед отображением курсор, который указывает на выбранный цвет.|  
  
## <a name="remarks"></a>Примечания  
 Стандартные цвета выбираются из палитры цветов шестиугольник и пользовательские цвета выбираются из панель яркости где цвета задаются с помощью красного, зеленого и синего нотации или нотации оттенка/satuaration и яркости.  
  
 На следующем рисунке показаны некоторые `CMFCColorPickerCtrl` объектов.  
  
 ![Диалоговое окно для CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "colorpicker")  
  
 `CMFCColorPickerCtrl` Поддерживает две пары стили. Стили HEX и HEX_GREYSCALE подходят для стандартных цвет. Стили ВЫБОРА и ЯРКОСТИ подходят для выбора другой цвет.  
  
 Выполните следующие действия для включения `CMFCColorPickerCtrl` управления диалогового окна:  
  
1.  При использовании **ClassWizard**, вставьте новый элемент управления button в ваш шаблон диалогового окна (потому что `CMFCColorPickerCtrl` класс, наследуемый от `CButton` класса).  
  
2.  Вставьте переменную-член, которая связана с новый элемент управления button в классе диалогового окна. Измените тип переменной из `CButton` для `CMFCColorPickerCtrl`.  
  
3.  Вставить `WM_INITDIALOG` обработчик сообщений для класса диалогового окна. В обработчике задайте тип, палитры и начальный цвет выбранного `CMFCColorPickerCtrl` элемента управления.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует способы настройки `CMFCColorPickerCtrl` с использованием различных методов `CMFCColorPickerCtrl` класса. В примере показано, как задать тип элемента управления выбора и как задать цвет, цветового тона, яркости и насыщенности. Пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [Для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
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
 Вызывается платформой перед отображением курсор, который указывает на выбранный цвет.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Задает прямоугольную область вокруг выбранного цвета.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод изменить форму курсора, указывающий на выбранный цвет.  
  
##  <a name="getcolor"></a>  CMFCColorPickerCtrl::GetColor  
 Получает цвет, выбранного пользователем.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение выбранного цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethls"></a>  CMFCColorPickerCtrl::GetHLS  
 Извлечение значений цветового тона, яркости и насыщенности цвета, выбранного пользователем.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `hue`  
 Указатель на переменную типа double, получает сведения о цветовой тон.  
  
 [выходной] `luminance`  
 Указатель на переменную типа double, получающий сведения яркости.  
  
 [выходной] `saturation`  
 Указатель на переменную типа double, получающий насыщенность сведения.  
  
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
 Возвращает компонент яркости цвета, выбранного пользователем.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Компонент яркости выбранного цвета.  
  
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
 Задает текущий цвет цвет определяется указанным компонентов цвета RGB или шестиугольник указанной ячейки.  
  
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
 [in] `R`  
 Компонент красного цвета.  
  
 [in] `G`  
 Компонент зеленого цвета.  
  
 [in] `B`  
 Компонент синего цвета.  
  
 [in] `x`  
 Координата по оси x курсор, который указывает на шестиугольник ячейки.  
  
 [in] `y`  
 Координата по оси y курсор, который указывает на шестиугольник ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вторая перегрузка этого метода всегда возвращает `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Первая перегрузка этого метода задает текущий цвет цвет, который соответствует элементу управления выбора цвета, заданные компонентов красного, зеленого и синего цвета.  
  
 Вторая перегрузка этого метода задает текущий цвет в цвет ячейки шестиугольник, который указывает, позиции указанного курсора.  
  
##  <a name="setcolor"></a>  CMFCColorPickerCtrl::SetColor  
 Задает текущий цвет указанное значение цвета RGB.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Color`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sethls"></a>  CMFCColorPickerCtrl::SetHLS  
 Задает текущий цвет с указанным значением цвета HLS.  
  
```  
void SetHLS(
    double hue,  
    double luminance,  
    double saturation,  
    BOOL bInvalidate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hue`  
 Значение оттенка.  
  
 [in] `luminance`  
 Значение яркости.  
  
 [in] `saturation`  
 Значение насыщенности.  
  
 [in] `bInvalidate`  
 `TRUE` Чтобы принудительно окно немедленно обновить новый цвет; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sethue"></a>  CMFCColorPickerCtrl::SetHue  
 Изменяет оттенок выбранный цвет.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Hue`  
 Значение оттенка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setluminance"></a>  CMFCColorPickerCtrl::SetLuminance  
 Изменяет яркости выбранного цвета.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Luminance`  
 Значение яркости.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setluminancebarwidth"></a>  CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Задает ширину линейки яркости в средстве выбора цвета.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `w`  
 Ширина полосы яркости измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы изменить размеры панели яркости, расположенного на **настраиваемый** вкладку элемента управления выбора цвета. `w` Параметр задает новую ширину панель яркости. Значение ширины учитывается, если она превышает три четверти Ширина клиентской области.  
  
##  <a name="setoriginalcolor"></a>  CMFCColorPickerCtrl::SetOriginalColor  
 Задает начальный выбранного цвета.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ref`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при инициализации элемента управления выбора цвета.  
  
##  <a name="setpalette"></a>  CMFCColorPickerCtrl::SetPalette  
 Задает текущую палитру цветов.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPalette`  
 Указатель на цветовой палитры.  
  
### <a name="remarks"></a>Примечания  
 Цветовая палитра определяет массив цветов, которые отображаются в средстве выбора цвета.  
  
##  <a name="setsaturation"></a>  CMFCColorPickerCtrl::SetSaturation  
 Изменяет насыщенности выбранного цвета.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Saturation`  
 Значение насыщенности.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settype"></a>  CMFCColorPickerCtrl::SetType  
 Задает тип элемента управления выбора цвета для отображения.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colorType`  
 Тип элемента управления выбора цвета.  
  
 Типы определяются `CMFCColorPickerCtrl::COLORTYPE` перечисления. Допустимые типы `LUMINANCE`, `PICKER`, `HEX` и `HEX_GREYSCALE`. Значение по умолчанию — `PICKER`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы указать тип элемента управления выбора цвета, этот метод вызывается до создания элемента управления Windows.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)
