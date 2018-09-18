---
title: Класс CMFCRibbonEdit | Документация Майкрософт
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
ms.openlocfilehash: c96b5b18530cd9b983e5a4c022883919261cc22c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701614"
---
# <a name="cmfcribbonedit-class"></a>Класс CMFCRibbonEdit
Реализует элемент управления, расположенный на панели ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Создает объект `CMFCRibbonEdit`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Указывает, является ли высоту `CMFCRibbonEdit` элемент управления может увеличиваться по вертикали в высоту строки ленты.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Создает объект `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Копирует состояние указанного `CMFCRibbonEdit` объект с текущим `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|Создает новое текстовое поле для `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Уничтожает `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Раскрывающееся поле со списком.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Включает и задает диапазон кнопка "Счетчик" для текстового поля.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Получает размер compact `CFMCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Извлекает текст в текстовом поле.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Получает размер промежуточных `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Извлекает выравнивание текста в текстовом поле.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Получает ширину в пикселях от `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Указывает ли отображение размер для `CMFCRibbonEdit` элемент управления может быть compact.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Указывает, является ли `CMFCRIbbonEdit` управления имеет фокус.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Указывает ли отображение размер для `CMFCRibbonEdit` элемент управления может быть большим.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Указывает, имеет ли текстовое поле счетчика.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Указывает, является ли `CMFCRibbonEdit` элемент управления выделяется.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Вызывается платформой при размеры прямоугольника, отображаемое `CMFCRibbonEdit` управления изменениями.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Вызывается платформой для отрисовки `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Вызывается платформой для рисования метки и изображения для `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Вызывается платформой для отрисовки `CMFCRibbonEdit` элемента управления в поле со списком команд.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Вызывается платформой для включения или отключения `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Вызывается платформой, когда указатель мыши входит или выходит за границы `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает подсказки клавиши и `CMFCRibbonEdit` управления имеет фокус.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Вызывается платформой для обновления `CMFCRibbonEdit` управления, когда пользователь нажимает левую кнопку мыши на элементе управления.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Вызывается платформой, когда пользователь отпускает левую кнопку мыши.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Вызывается платформой для обновления `CMFCRibbonEdit` управления при изменении направление макета.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Вызывается платформой для отображения или скрытия `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Обновляет отображение `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Задает данные специальных возможностей для `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Задает текст в текстовом поле.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Задает выравнивание текста текстового поля.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Задает ширину текстового поля для `CMFCRibbonEdit` элемента управления.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется создание `CMFCRibbonEdit` , Показать кнопки стрелками рядом с элемента управления редактирования и задайте текст элемента управления. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 Указывает, является ли высоту [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления может увеличиваться по вертикали в высоту строки ленты.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение FALSE.  
  
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
*nID*<br/>
[in] ИД для команды `CMFCRibbonEdit` элемента управления.  
  
*nWidth*<br/>
[in] Ширина в пикселях, текстового поля для `CMFCRibbonEdit` элемента управления.  
  
*lpszLabel*<br/>
[in] Метка для `CMFCRibbonEdit` элемента управления.  
  
*Изображение*<br/>
[in] Индекс мелкое изображение для `CMFCRibbonEdit` элемента управления. Коллекция изображений небольшого размера, поддерживаемое родительской категории ленты.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonEdit` Элемент управления не использовать большое изображение.  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 Копирует состояние указанного [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объект с текущим [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Параметры  
*src*<br/>
[in] Источник `CMFCRibbonEdit` объекта.  
  
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
*pWndParent*<br/>
[in] Указатель на родительское окно `CMFCRibbonEdit` объекта.  
  
*dwEditStyle*<br/>
[in] Задает стиль текстового поля. Вы можете объединить стили окна, перечисленных в разделе "Примечания" с [изменение стилей элемента управления](/windows/desktop/Controls/edit-control-styles) , описанные в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новое текстовое поле, если метод был выполнен успешно; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для создания настраиваемого текстового поля.  
  
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
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод для раскрывающегося списка.  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 Включает и задает диапазон кнопка "Счетчик" для текстового поля.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
*Nмин.*<br/>
[in] Минимальное значение кнопка "Счетчик".  
  
*Nмакс.*<br/>
[in] Максимальное значение кнопка "Счетчик".  
  
### <a name="remarks"></a>Примечания  
 Кнопки "Счетчик" отобразить вверх и Стрелка вниз и пользователь может перемещаться через фиксированный набор значений.  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 Получает размер compact [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Compact размер `CMFCRibbonEdit` объекта.  
  
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
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Промежуточный размер `CMFCRibbonEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 Извлекает выравнивание текста в текстовом поле.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления выравнивание текста. Возможные значения в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение является одним из следующих стилей элемента управления редактирования:  
  
- **ES_LEFT** для выравнивание по левому краю  
  
- **ES_CENTER** для выравнивание по центру  
  
- **ES_RIGHT** для выравнивание по правому краю  
  
 Дополнительные сведения об этих стилей см. в разделе [изменение стилей элемента управления](/windows/desktop/Controls/edit-control-styles).  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 Получает ширину в пикселях от [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
*bInFloatyMode*<br/>
[in] Значение TRUE, если `CMFCRibbonEdit` элемент управления находится в режиме с плавающей запятой; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях от `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 Указывает ли отображение размер для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемент управления может быть compact.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает значение TRUE. Переопределите этот метод, чтобы указать, может ли быть compact размер экрана.  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 Указывает, является ли [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если `CMFCRibbonEdit` управления имеет фокус; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 Указывает ли отображение размер для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления может быть большим.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает значение FALSE. Переопределите этот метод, чтобы указать, может ли быть больших размеров.  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 Указывает, имеет ли текстовое поле счетчика.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текстовое поле имеет кнопка "Счетчик"; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 Указывает, является ли [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемент управления выделяется.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если `CMFCRibbonEdit` элемент управления выделен; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 Вызывается платформой при размеры прямоугольника, отображаемое [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления изменений.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 Вызывается платформой для отрисовки [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 Вызывается платформой для рисования метки и изображения для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 Вызывается платформой для отрисовки [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления в поле со списком команд.  
  
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
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
*strText*<br/>
[in] Отображаемый текст [ ] (../../mfc/reference/cmfcribbonedit-class.md "класс cmfcribbonedit").  
  
*nTextOffset*<br/>
[in] Расстояние в пикселях от левого края поле со списком для отображения текста.  
  
*Rect*<br/>
[in] Прямоугольник для отображения `CMFCRibbonEdit` элемента управления.  
  
*bIsSelected*<br/>
[in] Этот параметр не используется.  
  
*bHighlighted*<br/>
[in] Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 В списке команд отображаются элементы управления ленты, чтобы разрешить пользователям настраивать панели инструментов быстрого доступа.  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 Вызывается платформой для включения или отключения [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
*bEnable*<br/>
[in] Значение TRUE для включения элемента управления; Значение FALSE, чтобы отключить элемент управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 Вызывается платформой, когда указатель мыши входит или выходит за границы [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Параметры  
*bHighlight*<br/>
[in] Значение TRUE, если указатель мыши находится в границах `CMFCRibbonEdit` управления; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 Вызывается платформой, когда пользователь нажимает подсказки клавиши и [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Параметры  
*bIsMenuKey*<br/>
[in] Значение TRUE, если подсказки клавиши отображаются во всплывающем меню. в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если событие было обработано; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 Вызывается платформой для обновления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления, когда пользователь нажимает левую кнопку мыши на элементе управления.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 Вызывается платформой, когда пользователь отпускает левую кнопку мыши.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 Вызывается платформой для обновления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления при изменении направление макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
*bIsRTL*<br/>
[in] Значение TRUE, если макет справа налево; Значение FALSE, если макет слева направо.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 Вызывается платформой для отображения или скрытия [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
*bShow*<br/>
[in] Значение TRUE для отображения элемента управления; Значение FALSE для скрытия элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 Обновляет отображение [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод перерисовывает прямоугольник отображения для `CMFCRibbonEdit` путем вызова косвенно [CWnd::RedrawWindow](/windows/desktop/api/winuser/nf-winuser-redrawwindow) с флагами RDW_INVALIDATE RDW_ERASE и RDW_UPDATENOW значение.  
  
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
 Всегда возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 Задает текст в текстовом поле.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Параметры  
*strText*<br/>
[in] Текст для текстового поля.  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 Задает выравнивание текста текстового поля.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Параметры  
*nAlign*<br/>
[in] Значение перечисления выравнивание текста. Возможные значения в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Параметр *nAlign* является одним из следующих изменение стилей элемента управления:  
  
- ES_LEFT для выравнивание по левому краю  
  
- ES_CENTER для выравнивание по центру  
  
- ES_RIGHT для выравнивание по правому краю  
  
 Дополнительные сведения об этих стилей см. в разделе [изменение стилей элемента управления](/windows/desktop/Controls/edit-control-styles).  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 Задает ширину текстового поля для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемента управления.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
*nWidth*<br/>
[in] Ширина в пикселях, текстового поля.  
  
 *bInFloatyMode*  
 Значение TRUE, чтобы задать ширину для режима с плавающей запятой; Значение FALSE, чтобы задать ширину для обычного режима.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonEdit` Элемент управления имеет два значения ширины в зависимости от его режим отображения: с плавающей запятой обычным и полноэкранным режимом.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)