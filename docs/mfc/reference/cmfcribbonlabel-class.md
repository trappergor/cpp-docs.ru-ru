---
title: Класс CMFCRibbonLabel | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcbc552560325e844cf0812a3002088f829d6c60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonlabel-class"></a>Класс CMFCRibbonLabel
Реализует недоступную для щелчка текстовую метку для ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Создает и инициализирует `CMFCRibbonLabel` объект с указанной текстовой строки.|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonLabel::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Определяет, какие данные специальных возможностей для текущего элемента метки ленты. (Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
### <a name="remarks"></a>Примечания  
 После создания метку ленты, добавьте его на панель, вызвав [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
 Метка на ленте нельзя добавить на панель быстрого доступа.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonLabel.h  
  
##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel  
 Создает и инициализирует [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) объекта, который отображает заданную текстовую строку.  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
 Текст, отображаемый в метке.  
  
 [in] `bIsMultiLine`  
 `TRUE` Чтобы указать, что метка Многострочная метка; в противном случае `FALSE`.  
  
##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData  
 Определяет, какие данные специальных возможностей для текущего элемента метки ленты.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Представляет родительского окна текущую метку ленты.  
  
 [выходной] `data`  
 Объект типа `CAccessibilityData` заполняется данные специальных возможностей текущей метки ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если `data` параметр был заполнен данные специальных возможностей текущей метки ленты успешно, в противном случае — `FALSE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
