---
title: "Класс для CMFCColorPickerCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCColorPickerCtrl class
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0a819d04535ba965e2c1a10f3761c442c9840538
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpickerctrl-class"></a>Класс для CMFCColorPickerCtrl
`CMFCColorPickerCtrl` Класс предоставляет функциональные возможности для управления, который используется для выбора цветов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Создает объект `CMFCColorPickerCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Получает цвет, выбранный пользователем.|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Извлекает значения цветового тона, яркости и насыщенности цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Возвращает компонент оттенок цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Возвращает компонент яркости цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Возвращает компонент насыщенность цвета, выбранного пользователем.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Задает текущий цвет в цвет, определяемый указанным компонентов цвета RGB или шестиугольник указанной ячейки.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Задает текущий цвет указанное значение цвета RGB.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Задает текущий цвет указанное значение цвета HLS.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Изменяет компонента оттенка выбранного цвета.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Изменение яркости компонент выбранного цвета.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Задает ширину полосы яркости в элемент управления для выбора цвета.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Задает начальный выбранного цвета.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Задает текущую палитру цветов.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Изменяет компонента насыщенности выбранного цвета.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Задает тип элемента управления выбора цвета для отображения.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Вызывается средой перед отображением курсор, который указывает на выбранный цвет.|  
  
## <a name="remarks"></a>Примечания  
 Стандартные цвета выбираются из шестигранной цветовой палитры, а также пользовательские цвета выбираются из панель яркости где цвета задаются с помощью красного, зеленого и синего нотации или нотации satuaration/цветового тона и яркости.  
  
 На следующем рисунке показано несколько `CMFCColorPickerCtrl` объектов.  
  
 ![Диалоговое окно для CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "colorpicker")  
  
 `CMFCColorPickerCtrl` Поддерживает две пары стили. Стили HEX и HEX_GREYSCALE подходят для стандартный цвет выделения. Выбор и ЯРКОСТЬЮ стили подходят для выбора пользовательского цвета.  
  
 Выполните следующие действия для включения `CMFCColorPickerCtrl` управления диалогового окна:  
  
1.  При использовании **ClassWizard**, вставьте новый элемент управления button в ваш шаблон диалогового окна (поскольку `CMFCColorPickerCtrl` класс, наследуемый от `CButton` класса).  
  
2.  Вставка переменной-члена, который связан с новый элемент управления button в классе диалогового окна. Измените тип переменной из `CButton` в `CMFCColorPickerCtrl`.  
  
3.  Вставить `WM_INITDIALOG` обработчик сообщений для класса диалогового окна. В обработчике задайте тип, палитры и начальный цвет выбранного `CMFCColorPickerCtrl` элемента управления.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить `CMFCColorPickerCtrl` объектов с помощью различных методов в `CMFCColorPickerCtrl` класса. В примере показано, как задать тип элемента управления выбора и как задать цвет, оттенка, яркости и насыщенности. Пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#4;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#5;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [Для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolorpickerctrl.h  
  
##  <a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 Создает объект `CMFCColorPickerCtrl`.  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor  
 Вызывается средой перед отображением курсор, который указывает на выбранный цвет.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Определяет прямоугольную область вокруг выбранного цвета.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод изменить форму курсор, указывающий на выбранный цвет.  
  
##  <a name="getcolor"></a>CMFCColorPickerCtrl::GetColor  
 Получает цвет, выбранный пользователем.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение выбранного цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethls"></a>CMFCColorPickerCtrl::GetHLS  
 Извлекает значения цветового тона, яркости и насыщенности цвета, выбранного пользователем.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `hue`  
 Указатель на переменную типа double, получающий сведения цветовой тон.  
  
 [выходной] `luminance`  
 Указатель на переменную типа double, получающий сведения яркости.  
  
 [выходной] `saturation`  
 Указатель на переменную типа double, получающий насыщенность сведения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethue"></a>CMFCColorPickerCtrl::GetHue  
 Возвращает компонент оттенок цвета, выбранного пользователем.  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Компонент оттенка выбранного цвета.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getluminance"></a>CMFCColorPickerCtrl::GetLuminance  
 Возвращает компонент яркости цвета, выбранного пользователем.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Компонент яркости выбранного цвета.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getsaturation"></a>CMFCColorPickerCtrl::GetSaturation  
 Получает значение насыщенности цвета, выбранного пользователем.  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Компонент насыщенности выбранного цвета.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon  
 Задает текущий цвет в цвет, определяемый указанным компонентов цвета RGB или шестиугольник указанной ячейки.  
  
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
 Компонент красным цветом.  
  
 [in] `G`  
 Компонент зеленым цветом.  
  
 [in] `B`  
 Компонент синий цвет.  
  
 [in] `x`  
 X координата курсора, который указывает на шестиугольник ячейки.  
  
 [in] `y`  
 Координата по оси y курсора, который указывает на шестиугольник ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вторая перегрузка этого метода всегда возвращает `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Первая перегрузка этого метода задает текущий цвет цвет, соответствующий элемент выбора цвета, заданного компонентов красного, зеленого и синего цвета.  
  
 Вторая перегрузка этого метода задается цвет шестиугольник ячейки, который указывает текущий цвет по позиции указанного курсора.  
  
##  <a name="setcolor"></a>CMFCColorPickerCtrl::SetColor  
 Задает текущий цвет указанное значение цвета RGB.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Color`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sethls"></a>CMFCColorPickerCtrl::SetHLS  
 Задает текущий цвет указанное значение цвета HLS.  
  
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
 `TRUE`Чтобы принудительно окна, чтобы немедленно обновить новый цвет; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sethue"></a>CMFCColorPickerCtrl::SetHue  
 Изменение оттенка выбранного цвета.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Hue`  
 Значение оттенка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance  
 Изменение яркости выбранного цвета.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Luminance`  
 Значение яркости.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Задает ширину полосы яркости в элемент управления для выбора цвета.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `w`  
 Ширина линейки яркости измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы изменить размер панели яркости на **пользовательские** вкладку элемента управления для выбора цвета. `w` Параметр задает новую ширину полосы яркости. Значение ширины учитывается, если она превышает три четверти Ширина клиентской области.  
  
##  <a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor  
 Задает начальный выбранного цвета.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ref`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при инициализации элемент управления для выбора цвета.  
  
##  <a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette  
 Задает текущую палитру цветов.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPalette`  
 Указатель на цветовой палитры.  
  
### <a name="remarks"></a>Примечания  
 Цветовая палитра определяет массив цветов, представленных в элемент управления для выбора цвета.  
  
##  <a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation  
 Изменяет насыщенности выбранного цвета.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Saturation`  
 Значение насыщенности.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settype"></a>CMFCColorPickerCtrl::SetType  
 Задает тип элемента управления выбора цвета для отображения.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colorType`  
 Тип элемента управления выбора цвета.  
  
 Типы определяются `CMFCColorPickerCtrl::COLORTYPE` перечисления. Допустимые типы `LUMINANCE`, `PICKER`, `HEX` и `HEX_GREYSCALE`. Значение по умолчанию — `PICKER`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы указать тип элемента управления выбора цвета, этот метод вызывается до создается элемент управления Windows.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

