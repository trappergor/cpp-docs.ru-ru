---
title: "Структура CMFCTabToolTipInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CMFCTabToolTipInfo
dev_langs: C++
helpviewer_keywords: CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cfb12ca9660259a4451d2841a921a566cf54505
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctabtooltipinfo-structure"></a>Структура CMFCTabToolTipInfo
Эта структура предоставляет сведения о вкладке MDI, на который наведен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>Участники  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Указывает индекс элемента управления tab.|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Указатель на элемент управления вкладки.|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Текст всплывающей подсказки.|  
  
## <a name="remarks"></a>Примечания  
 Указатель на `CMFCTabToolTipInfo` структуры передается как параметр `AFX_WM_ON_GET_TAB_TOOLTIP` сообщения. Это сообщение появляется в том случае, если включены вкладках MDI и наведении указателя мыши на элемент управления вкладки.  
  
## <a name="example"></a>Пример  
 В следующем примере показан способ `CMFCTabToolTipInfo` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasetabctrl.h  
  
##  <a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex  
 Указывает индекс элемента управления tab.  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>Примечания  
 Индекс вкладки, по которому пользователь перемещается.  
  
### <a name="example"></a>Пример  
 В следующем примере показан способ `m_nTabIndex` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd  
 Указатель на элемент управления вкладки.  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>Пример  
 В следующем примере показан способ `m_pTabWnd` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText  
 Текст всплывающей подсказки.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Примечания  
 Если строка является пустым, всплывающая подсказка не отображается.  
  
### <a name="example"></a>Пример  
 В следующем примере показан способ `m_strText` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
