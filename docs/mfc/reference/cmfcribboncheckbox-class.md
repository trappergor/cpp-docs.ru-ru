---
title: "Класс CMFCRibbonCheckBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCheckBox class
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
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
ms.openlocfilehash: 9efe04a8e79835b8e51b7045cb86ab2dba68b675
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncheckbox-class"></a>Класс CMFCRibbonCheckBox
Класс `CMFCRibbonCheckBox` реализует флажок, который можно добавить на панель ленты, панель быстрого доступа или во всплывающее меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Переопределяет [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Переопределяет [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|  
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Переопределяет [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Переопределяет `CMFCRibbonButton::IsDrawTooltipImage`.)|  
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Переопределяет [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Переопределяет [CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|  
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Переопределяет `CMFCRibbonButton::OnDrawOnList`.)|  
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать класс `CMFCRibbonCheckBox` в вашем приложении, добавьте в код следующий конструктор:  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
где `nID` — идентификатор команды флажка, `lpszText` — текстовая метка флажка.  
  
 Флажок можно добавить на панель ленты с помощью [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncheckbox.h  
  
##  <a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox  
 Конструктор объекта флажок ленты  
  
```  
CMFCRibbonCheckBox(
    UINT nID,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Указывает идентификатор команды.  
  
 [in] `lpszText`  
 Задает текст метки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Создает объект флажок ленты.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCRibbonCheckBox` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&17;](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize  
 При переопределении возвращает компактные размеры элемента управления checkbox.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на `CDC` связанного с флажком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CSize` , содержащий компактные размеры элемента управления checkbox.  
  
### <a name="remarks"></a>Примечания  
 Если не переопределен, возвращает промежуточный размер элемента управления checkbox.  
  
##  <a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize  
 Получает размер промежуточного элемента управления checkbox.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на `CDC` связан этот флажок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` объект, содержащий промежуточные размер элемента управления checkbox.  
  
### <a name="remarks"></a>Примечания  
 Если не переопределен, вычисляет промежуточный размер размер по умолчанию флажок ( `AFX_CHECK_BOX_DEFAULT_SIZE`) плюс размер текста, а также поля.  
  
##  <a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize  
 Возвращает обычного размера элемента управления checkbox.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на `CDC` объект, связанный с этот флажок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CSize` , содержащий обычного размера элемента управления checkbox.  
  
### <a name="remarks"></a>Примечания  
 Если не переопределен, возвращает промежуточный размер элемента управления checkbox.  
  
##  <a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage  
 Указывает, существует ли подсказки изображения, связанного с флажком.  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` при наличии подсказки изображения, связанного с флажком, или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>CMFCRibbonCheckBox::OnDraw  
 Вызывается платформой для рисования флажок, с помощью заданного контекста устройств.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на `CDC` для рисования флажок.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OnDrawMenuImage  
 Вызывается платформой для отрисовки меню изображений для флажка.  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDC*`  
 Указатель на `CDC` связанного с флажком.  
  
 [in] `CRect`  
 Объект `CRect` объект, задающий прямоугольник, в котором будет размещено изображение меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если рисования изображения, или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
 Если не переопределен, возвращает `FALSE`.  
  
##  <a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawOnList  
 Вызывается платформой для рисования флажок в поле со списком команд.  
  
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
 Указатель на контекст устройства, в котором отображается флажок.  
  
 [in] `strText`  
 Отображаемый текст.  
  
 [in] `nTextOffset`  
 Расстояние в точках с левой стороны окна списка для отображения текста.  
  
 [in] `rect`  
 Прямоугольник отображения флажка.  
  
 [in] `bIsSelected`  
 `TRUE`Если флажок установлен, или `FALSE` Если нет.  
  
 [in] `bHighlighted`  
 `TRUE`Если флажок выделен, или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData  
 Задает данные специальных возможностей для флажка.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 `pParent`  
 Родительское окно флажок.  
  
 `data`  
 Данные специальных возможностей для флажка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод задает специальные данные флажка и всегда возвращает `TRUE`. Переопределите этот метод, чтобы задать данные специальных возможностей и возвращать значение, указывающее на успешное или неуспешное выполнение.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

