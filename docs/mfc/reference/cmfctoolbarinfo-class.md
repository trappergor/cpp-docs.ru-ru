---
title: "Класс CMFCToolBarInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarInfo class
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a9e66ffa0b5a751a7e5711ed20927a6adcede45d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarinfo-class"></a>Класс CMFCToolBarInfo
Содержит идентификаторы ресурса изображений панели инструментов в различных состояниях. `CMFCToolBarInfo`Представляет вспомогательный класс, который используется в качестве параметра [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>Члены  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Идентификатор ресурса растрового изображения панели инструментов, содержащее изображения регулярных (холодные) панели инструментов.|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Идентификатор ресурса растрового изображения панели инструментов, содержащий изображений отключено панели инструментов.|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Идентификатор ресурса растрового изображения панели инструментов, содержащее изображения выбранной панели инструментов (активные).|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Идентификатор ресурса точечного рисунка панели инструментов, содержит большие, обычных инструментов изображения.|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Идентификатор ресурса растрового изображения панели инструментов, содержащий большой, отключить изображений на панели инструментов.|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Идентификатор ресурса растрового изображения панели инструментов, содержащий большой, выбранных изображений на панели инструментов.|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Идентификатор ресурса растрового изображения панели инструментов, содержащее изображения запрещенным.|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Идентификатор ресурса растрового изображения панели инструментов меню изображениями.|  
  
## <a name="remarks"></a>Примечания  
 Битовая карта инструментов полностью состоит из изображений на панели инструментов small (кнопки) фиксированного размера. Каждый идентификатор ресурса, который хранится в `CMFCToolBarInfo` объекта является точечным рисунком, содержащий полный набор инструментов образов в одном состоянии (для примера, выбранные отключено, большой размер или меню изображений).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 Указывает идентификатор ресурса для всех образов обычная кнопка панели инструментов.  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 Указывает идентификатор ресурса для образов недоступной кнопку панели инструментов.  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 Указывает идентификатор ресурса для всех образов выделенной кнопки панели инструментов.  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 Указывает идентификатор ресурса для всех изображений больших обычная кнопка панели инструментов.  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 Указывает идентификатор ресурса для всех изображений больших отключенной кнопки панели инструментов.  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 Указывает идентификатор ресурса для всех больших изображений выделенной панели инструментов.  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 Указывает идентификатор ресурса для образов, команда недоступна на панели инструментов.  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 Указывает идентификатор ресурса для всех обычных изображений пунктов меню на панели инструментов.  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

