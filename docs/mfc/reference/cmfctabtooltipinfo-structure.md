---
title: "Структура CMFCTabToolTipInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
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
ms.openlocfilehash: b9750cd9369313a3ed6ea9474d401cd0068a75fa
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabtooltipinfo-structure"></a>Структура CMFCTabToolTipInfo
Эта структура содержит сведения о вкладке MDI, на которую наведен курсор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>Члены  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Указывает индекс элемента управления вкладками.|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Указатель вкладок элемента управления.|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Текст подсказки.|  
  
## <a name="remarks"></a>Примечания  
 Указатель на `CMFCTabToolTipInfo` структуры передается как параметр `AFX_WM_ON_GET_TAB_TOOLTIP` сообщение. Это сообщение появляется в том случае, если включены вкладками MDI и наведении указателя мыши на элемент управления вкладками.  
  
## <a name="example"></a>Пример  
 В следующем примере показан способ `CMFCTabToolTipInfo` используется в [образце MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasetabctrl.h  
  
##  <a name="a-namemntabindexa--cmfctabtooltipinfomntabindex"></a><a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex  
 Указывает индекс элемента управления вкладками.  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>Примечания  
 Индекс вкладки, через который наведен.  
  
### <a name="example"></a>Пример  
 В следующем примере показан способ `m_nTabIndex` используется в [образце MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemptabwnda--cmfctabtooltipinfomptabwnd"></a><a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd  
 Указатель вкладок элемента управления.  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>Пример  
 В следующем примере показан способ `m_pTabWnd` используется в [образце MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemstrtexta--cmfctabtooltipinfomstrtext"></a><a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText  
 Текст подсказки.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Примечания  
 Если строка пуста, подсказка не отображается.  
  
### <a name="example"></a>Пример  
 В следующем примере показан способ `m_strText` используется в [образце MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

