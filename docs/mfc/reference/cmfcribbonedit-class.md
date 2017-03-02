---
title: "Класс CMFCRibbonEdit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit class
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 03eb96bf971b53a2100e6f93bac2f0641f0298e1
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonedit-class"></a>Класс CMFCRibbonEdit
Реализует элемент управления редактированием, расположенный на ленту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Создает объект `CMFCRibbonEdit`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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
|[CMFCRibbonEdit::GetWidth](#getwidth)|Получает ширину в пикселях `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Указывает размер ли отображение для `CMFCRibbonEdit` элемент управления может быть compact.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Указывает, является ли `CMFCRIbbonEdit` управления имеет фокус.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Указывает размер ли отображение для `CMFCRibbonEdit` элемента управления может быть большим.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Указывает, имеет ли поле счетчика.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Указывает, является ли `CMFCRibbonEdit` управления выделяется.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Вызывается инфраструктурой при размеры прямоугольника отображения для `CMFCRibbonEdit` контроля изменений.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Вызывается платформой для рисования `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Вызывается платформой для рисования метки и изображения для `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Вызывается платформой для рисования `CMFCRibbonEdit` элемента управления в поле со списком команд.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Вызывается платформой для включения или отключения `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Вызывается платформой, когда указатель мыши входит или выходит за границы `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает значение свойства keytip и `CMFCRibbonEdit` управления имеет фокус.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Вызывается платформой для обновления `CMFCRibbonEdit` управления при нажатии левой кнопки мыши на элементе управления.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Вызывается инфраструктурой при отпускании пользователем левой кнопки мыши.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Вызывается платформой для обновления `CMFCRibbonEdit` управления при изменении направления макета.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Вызывается платформой для отображения или скрытия `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Обновляет отображение `CMFCRibbonEdit` элемента управления.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Задает доступность данных для `CMFCRibbonEdit` объекта.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Задает текст в текстовом поле.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Задает выравнивание текста в текстовом поле.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Задает ширину текстового поля для `CMFCRibbonEdit` элемента управления.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCRibbonEdit` , Показать счетчик кнопки рядом с элемента управления поля ввода и задайте текст элемента управления. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonEdit.h  
  
##  <a name="a-namecanbestretcheda--cmfcribboneditcanbestretched"></a><a name="canbestretched"></a>CMFCRibbonEdit::CanBeStretched  
 Указывает, является ли высота [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления может увеличиваться по вертикали в высоту строки ленты.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecmfcribbonedita--cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a>CMFCRibbonEdit::CMFCRibbonEdit  
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
 [in] `nID`  
 ИД для команды `CMFCRibbonEdit` элемента управления.  
  
 [in] `nWidth`  
 Ширина в пикселях текстовое поле для `CMFCRibbonEdit` элемента управления.  
  
 [in] `lpszLabel`  
 Метка для `CMFCRibbonEdit` элемента управления.  
  
 [in] `nImage`  
 Индекс небольшое изображение для `CMFCRibbonEdit` элемента управления. Коллекция изображений небольшого размера, поддерживаемое ленты родительской категории.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonEdit` Большое изображение не используются для управления.  
  
##  <a name="a-namecopyfroma--cmfcribboneditcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonEdit::CopyFrom  
 Копирует состояние указанного [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объект с текущим [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Исходный объект `CMFCRibbonEdit`.  
  
### <a name="remarks"></a>Примечания  
 `src` Параметр должен иметь тип `CMFCRibbonEdit`.  
  
##  <a name="a-namecreateedita--cmfcribboneditcreateedit"></a><a name="createedit"></a>CMFCRibbonEdit::CreateEdit  
 Создает новое текстовое поле для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно элемента `CMFCRibbonEdit` объекта.  
  
 [in] `dwEditStyle`  
 Задает стиль текстового поля. Можно объединить стили окна, перечисленных в разделе «Примечания» с [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464) , описаны в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новое текстовое поле, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для создания настраиваемого текстового поля.  
  
 Можно применить следующие [стили окна](../../mfc/reference/window-styles.md) в текстовое поле:  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="a-namedestroyctrla--cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a>CMFCRibbonEdit::DestroyCtrl  
 Уничтожает [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedropdownlista--cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a>CMFCRibbonEdit::DropDownList  
 Раскрывающееся поле со списком.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод в раскрывающемся поле со списком.  
  
##  <a name="a-nameenablespinbuttonsa--cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a>CMFCRibbonEdit::EnableSpinButtons  
 Включает и настраивает диапазон счетчиком для текстового поля.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMin`  
 Минимальное значение счетчиком.  
  
 [in] `nMax`  
 Максимальное значение счетчиком.  
  
### <a name="remarks"></a>Примечания  
 Кнопками счетчика отображения вверх и Стрелка вниз и предоставить пользователям возможность перемещаться по фиксированный набор значений.  
  
##  <a name="a-namegetcompactsizea--cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonEdit::GetCompactSize  
 Получает размер compact [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Compact размер `CMFCRibbonEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetedittexta--cmfcribboneditgetedittext"></a><a name="getedittext"></a>CMFCRibbonEdit::GetEditText  
 Извлекает текст в текстовом поле.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст в текстовом поле.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetintermediatesizea--cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonEdit::GetIntermediateSize  
 Получает размер промежуточных [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер промежуточного `CMFCRibbonEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettextaligna--cmfcribboneditgettextalign"></a><a name="gettextalign"></a>CMFCRibbonEdit::GetTextAlign  
 Получает выравнивание текста в текстовом поле.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления для выравнивания текста. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение является одним из следующих стилей элемента управления редактирования:  
  
- **ES_LEFT** для выравнивания по левому краю  
  
- **ES_CENTER** для выравнивание по центру  
  
- **ES_RIGHT** для выравнивание по правому краю  
  
 Дополнительные сведения об этих стилях см. в разделе [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="a-namegetwidtha--cmfcribboneditgetwidth"></a><a name="getwidth"></a>CMFCRibbonEdit::GetWidth  
 Получает ширину в пикселях, [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bInFloatyMode`  
 `TRUE`Если `CMFCRibbonEdit` управления находится в режиме с плавающей запятой; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehascompactmodea--cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonEdit::HasCompactMode  
 Указывает размер ли отображение для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) элемент управления может быть compact.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`. Переопределите этот метод, чтобы указать, можно ли размер отображения compact.  
  
##  <a name="a-namehasfocusa--cmfcribbonedithasfocus"></a><a name="hasfocus"></a>CMFCRibbonEdit::HasFocus  
 Указывает, является ли [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `CMFCRibbonEdit` управления имеет фокус; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehaslargemodea--cmfcribbonedithaslargemode"></a><a name="haslargemode"></a>CMFCRibbonEdit::HasLargeMode  
 Указывает размер ли отображение для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления может быть большим.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `FALSE`. Переопределите этот метод, чтобы указать, может ли быть большого размера экрана.  
  
##  <a name="a-namehasspinbuttonsa--cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a>CMFCRibbonEdit::HasSpinButtons  
 Указывает, имеет ли поле счетчика.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если текстовое поле имеет счетчиком; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameishighlighteda--cmfcribboneditishighlighted"></a><a name="ishighlighted"></a>CMFCRibbonEdit::IsHighlighted  
 Указывает, является ли [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления выделяется.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `CMFCRibbonEdit` управления выделенным; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonafterchangerecta--cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a>CMFCRibbonEdit::OnAfterChangeRect  
 Вызывается инфраструктурой при размеры прямоугольника отображения для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) контроля изменений.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawa--cmfcribboneditondraw"></a><a name="ondraw"></a>CMFCRibbonEdit::OnDraw  
 Вызывается платформой для рисования [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawlabelandimagea--cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a>CMFCRibbonEdit::OnDrawLabelAndImage  
 Вызывается платформой для рисования метки и изображения для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawonlista--cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonEdit::OnDrawOnList  
 Вызывается платформой для рисования [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления в поле со списком команд.  
  
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
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCRibbonEdit` элемента управления.  
  
 [in] `strText`  
 Отображаемый текст [ ](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit class").  
  
 [in] `nTextOffset`  
 Расстояние в точках с левой стороны окна списка для отображения текста.  
  
 [in] `rect`  
 Прямоугольник для отображения `CMFCRibbonEdit` элемента управления.  
  
 [in] `bIsSelected`  
 Этот параметр не используется.  
  
 [in] `bHighlighted`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 Команды выводится список элементов управления ленты, чтобы пользователи могли настроить панель быстрого доступа.  
  
##  <a name="a-nameonenablea--cmfcribboneditonenable"></a><a name="onenable"></a>CMFCRibbonEdit::OnEnable  
 Вызывается платформой для включения или отключения [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить элемент управления; `FALSE` отключить элемент управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonhighlighta--cmfcribboneditonhighlight"></a><a name="onhighlight"></a>CMFCRibbonEdit::OnHighlight  
 Вызывается платформой, когда указатель мыши входит или выходит за границы [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHighlight`  
 `TRUE`Если указатель мыши находится в границах `CMFCRibbonEdit` управления; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonkeya--cmfcribboneditonkey"></a><a name="onkey"></a>CMFCRibbonEdit::OnKey  
 Вызывается платформой, когда пользователь нажимает значение свойства keytip и [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsMenuKey`  
 `TRUE`Если значение свойства keytip отображаются во всплывающем меню. в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE`, если событие было обработано; в противном случае значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonlbuttondowna--cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a>CMFCRibbonEdit::OnLButtonDown  
 Вызывается платформой для обновления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления при нажатии левой кнопки мыши на элементе управления.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonlbuttonupa--cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a>CMFCRibbonEdit::OnLButtonUp  
 Вызывается инфраструктурой при отпускании пользователем левой кнопки мыши.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrtlchangeda--cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonEdit::OnRTLChanged  
 Вызывается платформой для обновления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления при изменении направления макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsRTL`  
 `TRUE`Если макет справа налево; `FALSE` Если макет справа налево.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonshowa--cmfcribboneditonshow"></a><a name="onshow"></a>CMFCRibbonEdit::OnShow  
 Вызывается платформой для отображения или скрытия [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 `TRUE`для отображения элемента управления; `FALSE` для скрытия элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameredrawa--cmfcribboneditredraw"></a><a name="redraw"></a>CMFCRibbonEdit::Redraw  
 Обновляет отображение [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод перерисовывает отображаемый прямоугольник для `CMFCRibbonEdit` , вызывая косвенно [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) с `RDW_INVALIDATE`, `RDW_ERASE`, и `RDW_UPDATENOW` установленными флагами.  
  
##  <a name="a-namesetaccdataa--cmfcribboneditsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonEdit::SetACCData  
 Задает доступность данных для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) объекта.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 `pParent`  
 Указатель на родительское окно для `CMFCRibbonEdit` объекта.  
  
 `data`  
 Доступность данных для `CMFCRibbonEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetedittexta--cmfcribboneditsetedittext"></a><a name="setedittext"></a>CMFCRibbonEdit::SetEditText  
 Задает текст в текстовом поле.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strText`  
 Текст для текстового поля.  
  
##  <a name="a-namesettextaligna--cmfcribboneditsettextalign"></a><a name="settextalign"></a>CMFCRibbonEdit::SetTextAlign  
 Задает выравнивание текста в текстовом поле.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nAlign`  
 Значение перечисления для выравнивания текста. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Параметр `nAlign` является одним из следующих редактирования стилей элемента управления:  
  
- **ES_LEFT** для выравнивания по левому краю  
  
- **ES_CENTER** для выравнивание по центру  
  
- **ES_RIGHT** для выравнивание по правому краю  
  
 Дополнительные сведения об этих стилях см. в разделе [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="a-namesetwidtha--cmfcribboneditsetwidth"></a><a name="setwidth"></a>CMFCRibbonEdit::SetWidth  
 Задает ширину текстового поля для [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nWidth`  
 Ширина в пикселях текстового поля.  
  
 `bInFloatyMode`  
 `TRUE`Чтобы задать ширину для режима с плавающей запятой; `FALSE` для задания ширины для обычный режим.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonEdit` Элемент управления имеет два значения ширины в зависимости от его режим отображения: с плавающей запятой или обычный режим.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
