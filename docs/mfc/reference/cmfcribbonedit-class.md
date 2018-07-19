---
title: Класс CMFCRibbonEdit | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a67696289603697ddac541382d63f989881afaf
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040864"
---
# <a name="cmfcribbonedit-class"></a>Класс CMFCRibbonEdit
Реализует элемент управления редактированием, расположенной на панели ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Создает объект `CMFCRibbonEdit`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Указывает, является ли высота `CMFCRibbonEdit` управления может увеличиваться по вертикали в высоту строки ленты.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Создает объект `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Копирует состояние указанного `CMFCRibbonEdit` объект с текущим `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|Создает новое текстовое поле для `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Уничтожает `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Раскрывающееся поле со списком.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Включает и настраивает диапазон счетчиком для текстового поля.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Получает размер compact `CFMCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Извлекает текст в текстовом поле.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Получает размер промежуточных `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Получает выравнивание текста в текстовом поле.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Получает ширину в пикселях от `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Указывает, является ли размер отображения `CMFCRibbonEdit` элемент управления может быть compact.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Указывает, является ли `CMFCRIbbonEdit` управления имеет фокус.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Указывает, является ли размер отображения `CMFCRibbonEdit` управления могут быть большими.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Указывает, имеет ли текстовое поле "Счетчик".|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Указывает, является ли `CMFCRibbonEdit` элемент управления выделяется.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Вызывается платформой при размеры прямоугольник для отображения `CMFCRibbonEdit` контроля изменений.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Вызывается платформой для отрисовки `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Вызывается платформой для отрисовки метки и изображения для `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Вызывается платформой для отрисовки `CMFCRibbonEdit` элемента управления в поле со списком команд.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Вызывается платформой для включения или отключения `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Вызывается платформой, когда указатель мыши попадает или выходит за пределы `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает keytip и `CMFCRibbonEdit` управления имеет фокус.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Вызывается платформой для обновления `CMFCRibbonEdit` управления при нажатии левой кнопки мыши на элементе управления.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Вызывается платформой, когда пользователь отпускает левую кнопку мыши.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Вызывается платформой для обновления `CMFCRibbonEdit` управления при изменении направление макета.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Вызывается платформой для отображения или скрытия `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Обновляет отображение `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Задает данные специальных возможностей для `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Задает текст в текстовом поле.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Задает выравнивание текста в текстовом поле.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Задает ширину текстового поля для `CMFCRibbonEdit` элемента управления.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCRibbonEdit` объекта и отображать кнопки управления "Счетчик" рядом с элементом управления изменить текст элемента управления редактирования. Этот фрагмент кода является частью [MS Office 2007 демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 Указывает, является ли высота [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления может увеличиваться по вертикали в высоту строки ленты.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit  
 Создает [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
CMFCRibbonEdit(
    UINT nID,  
    int nWidth,  
    LPCTSTR lpszLabel = NULL,  
    int nImage = -1);

CMFCRibbonEdit();
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nID*  
 ИД для команды `CMFCRibbonEdit` элемента управления.  
  
 [in] *nWidth*  
 Ширина в пикселях текстового поля для `CMFCRibbonEdit` элемента управления.  
  
 [in] *lpszLabel*  
 Метка для `CMFCRibbonEdit` элемента управления.  
  
 [in] *nImage*  
 Индекс мелкое изображение для `CMFCRibbonEdit` элемента управления. Коллекция изображений небольшого размера, поддерживаемое родительской категории ленты.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonEdit` Управления не использует большое изображение.  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 Копирует состояние указанного [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объект с текущим [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *src*  
 Исходный объект `CMFCRibbonEdit`.  
  
### <a name="remarks"></a>Примечания  
 *Src* параметр должен иметь тип `CMFCRibbonEdit`.  
  
##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit  
 Создает новое текстовое поле для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWndParent*  
 Указатель на родительское окно `CMFCRibbonEdit` объекта.  
  
 [in] *dwEditStyle*  
 Задает стиль для текстового поля. Можно объединять стили окна, перечисленных в разделе "Примечания" с [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464) , описанные в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новое текстовое поле, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для создания пользовательских текстового поля.  
  
 Можно применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) в текстовое поле:  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl  
 Уничтожает [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList  
 Раскрывающееся поле со списком.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод в раскрывающемся поле со списком.  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 Включает и настраивает диапазон счетчиком для текстового поля.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nMin*  
 Минимальное значение счетчиком.  
  
 [in] *nMax*  
 Максимальное значение счетчиком.  
  
### <a name="remarks"></a>Примечания  
 Счетчик кнопок отображения up и стрелку вниз и пользователи могли переходить по фиксированный набор значений.  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 Получает размер compact [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Компактный размер `CMFCRibbonEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText  
 Извлекает текст в текстовом поле.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст в текстовом поле.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize  
 Получает размер промежуточных [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер промежуточного `CMFCRibbonEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 Получает выравнивание текста в текстовом поле.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления выравнивание текста. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение является одним из следующих стилей элемента управления редактирования:  
  
- **ES_LEFT** для выравнивания по левому краю  
  
- **ES_CENTER** для выравнивание по центру  
  
- **ES_RIGHT** для выравнивание по правому краю  
  
 Дополнительные сведения об этих стилях см. в разделе [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 Получает ширину в пикселях от [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bInFloatyMode*  
 `TRUE` Если `CMFCRibbonEdit` управления находится в режиме с плавающей запятой; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях от `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 Указывает, является ли размер отображения [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемент управления может быть compact.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`. Переопределите этот метод, чтобы указать, можно ли размер экрана compact.  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 Указывает, является ли [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если `CMFCRibbonEdit` управления имеет фокус; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 Указывает, является ли размер отображения [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления могут быть большими.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `FALSE`. Переопределите этот метод, чтобы указать, может ли быть большой размер экрана.  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 Указывает, имеет ли текстовое поле "Счетчик".  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если текстовое поле имеет счетчиком; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 Указывает, является ли [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления выделяется.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если `CMFCRibbonEdit` управления выделенный; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 Вызывается платформой при размеры отображаемый прямоугольник для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления изменений.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 Вызывается платформой для отрисовки [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 Вызывается платформой для отрисовки метки и изображения для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 Вызывается платформой для отрисовки [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления в поле со списком команд.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
 [in] *strText*  
 Отображаемый текст [cmfcribbonedit класса](../../mfc/reference/cmfcribbonedit-class.md "").  
  
 [in] *nTextOffset*  
 Расстояние в пикселях с левой стороны от списка для отображения текста.  
  
 [in] *rect*  
 Прямоугольник для отображения `CMFCRibbonEdit` элемента управления.  
  
 [in] *bIsSelected*  
 Этот параметр не используется.  
  
 [in] *bHighlighted*  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 Команды выводится список элементов управления ленты, чтобы разрешить пользователям настраивать панели инструментов быстрого доступа.  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 Вызывается платформой для включения или отключения [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 `TRUE` Чтобы включить элемент управления; `FALSE` отключение элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 Вызывается платформой, когда указатель мыши попадает или выходит за пределы [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bHighlight*  
 `TRUE` Если указатель находится в границах `CMFCRibbonEdit` управления; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 Вызывается платформой, когда пользователь нажимает keytip и [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bIsMenuKey*  
 `TRUE` Если значение свойства keytip отображаются во всплывающем меню. в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE`, если событие было обработано; в противном случае значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 Вызывается платформой для обновления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления при нажатии левой кнопки мыши на элементе управления.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *точки*  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 Вызывается платформой, когда пользователь отпускает левую кнопку мыши.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *точки*  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 Вызывается платформой для обновления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления при изменении направление макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bIsRTL*  
 `TRUE` Если макет справа налево; `FALSE` Если макет справа налево.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 Вызывается платформой для отображения или скрытия [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bShow*  
 `TRUE` для отображения элемента управления. `FALSE` для скрытия элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 Обновляет отображение [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод перерисовывает отображаемый прямоугольник для `CMFCRibbonEdit` , вызывая косвенно [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) с `RDW_INVALIDATE`, `RDW_ERASE`, и `RDW_UPDATENOW` установленными флагами.  
  
##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData  
 Задает данные специальных возможностей для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 *pParent*  
 Указатель на родительское окно для `CMFCRibbonEdit` объекта.  
  
 *data*  
 Данные специальных возможностей для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 Задает текст в текстовом поле.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strText*  
 Текст для текстового поля.  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 Задает выравнивание текста в текстовом поле.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nAlign*  
 Значение перечисления выравнивание текста. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Параметр *nAlign* является одним из следующих изменение стилей элемента управления:  
  
- **ES_LEFT** для выравнивания по левому краю  
  
- **ES_CENTER** для выравнивание по центру  
  
- **ES_RIGHT** для выравнивание по правому краю  
  
 Дополнительные сведения об этих стилях см. в разделе [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 Задает ширину текстового поля для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nWidth*  
 Ширина в пикселях, текстового поля.  
  
 *bInFloatyMode*  
 `TRUE` для задания ширины для режиме с плавающей запятой. `FALSE` для задания ширины для обычный режим.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonEdit` Элемент управления имеет два значения ширины в зависимости от режима отображения: плавающей обычным и полноэкранным режимом.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)