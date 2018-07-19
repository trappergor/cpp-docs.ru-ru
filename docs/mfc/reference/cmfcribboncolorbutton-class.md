---
title: Класс CMFCRibbonColorButton | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0966faee52febce026028fc6a93e611983ff61cb
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853583"
---
# <a name="cmfcribboncolorbutton-class"></a>класс CMFCRibbonColorButton
Класс `CMFCRibbonColorButton` реализует кнопку цвета, которую можно добавить на панель ленты. Кнопка цвета ленты отображает раскрывающееся меню, содержащее одну или несколько палитр.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Добавляет группу цветов в стандартную область цветов.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Указывает, нажата ли кнопка **Автоматически** .|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Активирует кнопку **Другие** .|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|Возвращает выбранный в данный момент цвет.|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Возвращает размер цветовых элементов, отображаемых на цветовой панели.|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Возвращает цвет элемента, выбранного в данный момент во всплывающей цветовой палитре.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Удаляет все группы цветов из стандартной области цветов.|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|Выбирает цвет в стандартной области цветов.|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Задает размер всех цветовых элементов, отображаемых на цветовой панели.|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Задает список значений RGB, которые должны отображаться в области цветов документа.|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>Примечания  
 Когда пользователь нажимает кнопку цвета на ленте, отображается цветовая панель. По умолчанию эта панель содержит палитру выбора цвета, называемую стандартной областью цветов. Помимо этого, цветовая панель может содержать кнопку **Автоматически** , которая позволяет пользователю выбрать цвет по умолчанию, и кнопку **Другие** , которая позволяет открыть всплывающую цветовую палитру с дополнительными цветами.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonColorButton` . В нем показано, как создать объект `CMFCRibbonColorButton` , задать большое изображение, активировать кнопку **Автоматически** , активировать кнопку **Другие** , задать число столбцов, задать размер всех цветовых элементов, отображаемых на цветовой панели, добавить группу цветов в стандартную область цветов и указать список значений RGB, которые должны отображаться в области цветов документа. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup  
 Добавляет группу цветов в стандартную область цветов.  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszName*  
 Имя группы.  
  
 [in] *lstColors*  
 Список цветов.  
  
 [in] *bContiguousColumns*  
 Управляет отображением цвет элементов в группе. Значение TRUE, если цвет элементы отображаются без интервалы по вертикали. Если значение равно FALSE, элементы цвета отображаются с интервалы по вертикали.  
  
### <a name="remarks"></a>Примечания  
 Воспользовавшись этой функцией, чтобы сделать цвет всплывающее отображать несколько групп цветов. Можно управлять как цвета отображаются в группе.  
  
##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton  
 Создает объект `CMFCRibbonColorButton`.  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nID*  
 Указывает идентификатор команды выполнения, когда пользователь нажимает кнопку команды.  
  
 [in] *lpszText*  
 Задает текст, отображаемый на кнопке.  
  
 [in] *nSmallImageIndex*  
 Отсчитываемый от нуля индекс небольшое изображение, отображаемый на кнопке.  
  
 [in] *цвет*  
 Цвет кнопки (по умолчанию используется черный).  
  
 [in] *bSimpleButtonLook*  
 Значение TRUE, если кнопки отображенный в виде простого прямоугольника.  
  
 [in] *nLargeImageIndex*  
 Отсчитываемый от нуля индекс большого изображения, отображаемый на кнопке.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton  
 Указывает, нажата ли кнопка **Автоматически** .  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszLabel*  
 Метка для **автоматического** кнопки.  
  
 [in] *colorAutomatic*  
 RGB-значение, указывающее **автоматического** цвет кнопки по умолчанию.  
  
 [in] *bEnable*  
 Значение TRUE, если **автоматического** кнопка доступна; Значение FALSE, если она отключена.  
  
 [in] *lpszToolTip*  
 Подсказку **автоматического** кнопки.  
  
 [in] *bOnTop*  
 Указывает ли **автоматического** кнопку стоит первым в списке, прежде чем цветовую палитру.  
  
 [in] *bDrawBorder*  
 Значение TRUE, если приложение рисует границу вокруг цветовой полосы на кнопку цвета на ленте. Цветовая панель отображает выбранный цвет. Значение FALSE, если приложение не создает обрамление  
  
##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton  
 Активирует кнопку **Другие** .  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszLabel*  
 Надпись на этой кнопке.  
  
 *lpszToolTip*  
 Текст подсказки для **других** кнопки.  
  
### <a name="remarks"></a>Примечания  
 **Других** кнопка является кнопкой, который отображается ниже группы цветов. Когда пользователь щелкает **других** кнопки, он отображает диалоговое окно цвета.  
  
##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor  
 Получает текущий цвет кнопки автоматически.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB, представляющий текущий цвет кнопки автоматически.  
  
### <a name="remarks"></a>Примечания  
 Цвет кнопки автоматически задается `colorAutomatic` параметр, передаваемый `CMFCRibbonColorButton::EnableAutomaticButton` метод.  
  
##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor  
 Возвращает выбранный в данный момент цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, выбранный, нажав кнопку.  
  
##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize  
 Возвращает размер цветовых элементов, отображаемых на цветовой панели.  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер кнопок цвет в раскрывающемся списке цветовой палитре.  
  
##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns  
 Возвращает количество элементов в строке коллекции отображения кнопка цвета ленты.  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество значков в каждой строке.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor  
 Возвращает цвет для выбранного элемента на всплывающее цветовую палитру.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет выбранного элемента на всплывающее цветовую палитру.  
  
##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups  
 Удаляет все группы цветов из стандартной области цветов.  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor  
 Выбирает цвет в стандартной области цветов.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *цвет*  
 Чтобы задать цвет.  
  
##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize  
 Задает размер всех цветовых элементов, отображаемых на цветовой панели.  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *sizeBox*  
 Новый размер кнопок цвет в палитре цветов.  
  
##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName  
 Задает новое имя для выбранного цвета.  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *цвет*  
 Значение цвета RGB.  
  
 [in] *strName*  
 Новое имя для указанного цвета.  
  
### <a name="remarks"></a>Примечания  
 Так как он вызывает `CMFCColorBar::SetColorName`, этот метод изменяет имя указанного цвета во всех `CMFCColorBar` объектов в приложении.  
  
##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns  
 Задает число столбцов, отображаемых в таблице цветов, представленные пользователю во время процесса выбора цвета для пользователя.  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nColumns*  
 Количество цветных значков для отображения в каждой строке.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors  
 Задает список значений RGB, которые должны отображаться в области цветов документа.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszLabel*  
 Текст, отображаемый с цветами документа.  
  
 [in] *lstColors*  
 Ссылка на список значений RGB.  
  
##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette  
 Указывает стандартные цвета для отображения в таблице цветов, который отображает кнопку цвета.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pPalette*  
 Указатель на цветовую палитру.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor  
 Вызывается платформой, когда пользователь выбирает цвет из цветовой таблицы отображается, когда пользователь нажимает кнопку цвета.  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *цвет*  
 Цвет, выбранный пользователем.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonColorButton::UpdateColor` Метод изменяет цвет выбранного кнопки и уведомляет родительского, отправив сообщение WM_COMMAND с уведомлением BN_CLICKED standard. Используйте [CMFCRibbonColorButton::GetColor](#getcolor) метод для извлечения выбранного цвета.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)
