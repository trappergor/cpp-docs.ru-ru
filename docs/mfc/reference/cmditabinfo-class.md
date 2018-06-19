---
title: Класс CMDITabInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
dev_langs:
- C++
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b95706603c8fe8a8f53be8cd0db405cd649271f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368099"
---
# <a name="cmditabinfo-class"></a>Класс CMDITabInfo
`CMDITabInfo` Класс используется для передачи параметров [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) метод. Задайте элементы этого класса, чтобы контролировать поведение групп вкладок MDI.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|Считывает этот объект из архива или записывает в него.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Указывает, является ли **закрыть** кнопка отображается в метке вкладки активной вкладки.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Указывает цвет вкладок MDI.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Указывает, отображаются ли в группу вкладок всплывающего меню, которое показывает список открытых документов или отображает кнопки прокрутки.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Указывает, можно ли пользователь менять положение вкладки путем перетаскивания.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Указывает, имеют ли вкладки плоский кадра.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Указывает, отображаются ли каждая метка вкладки **закрыть** кнопки.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Указывает, включены ли настраиваемые подсказки.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Указывает, следует ли отображать значки на вкладках MDI.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Указывает размер границы каждой вкладки окна.|  
|[CMDITabInfo::m_style](#m_style)|Задает стиль меток вкладок.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Указывает, расположены ли метки вкладок в верхней или нижней части страницы.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс задает параметры группы вкладок MDI, которые платформа создает.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для задания значений разных переменных-членов в `CMDITabInfo` класса.  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton;  
 Указывает, является ли **закрыть** кнопка отображается в метке вкладки активной вкладки.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, будет отображена надпись активной вкладки **закрыть** кнопки. **Закрыть** кнопка будет удалена из в правый верхний угол области вкладок. В противном случае не будет отображена надпись активной вкладки **закрыть** кнопки. **Закрыть** кнопка будет отображаться в правом верхнем углу области вкладок.  
  
##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor  
 Указывает, имеет ли каждая вкладка MDI свои собственные цвета.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, каждый будет иметь свои собственные цвета. Набор цветов, управляет библиотекой MFC. В противном случае вкладки отображаются в белый. Значение по умолчанию — `FALSE`.  
  
##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu  
 Указывает, отображаются ли каждая вкладка всплывающего меню, содержащее список открытых документов на правом краю области вкладок.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, windows Каждая вкладка отображает всплывающее меню, содержащее список открытых документов на правом краю области вкладок; В противном случае окно вкладки отображаются кнопки прокрутки на правом краю области вкладок. Значение по умолчанию — `FALSE`.  
  
##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap  
 Указывает, можно ли пользователь менять положение вкладки путем перетаскивания.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, пользователь может изменить положение вкладки вкладок путем их перетаскивания. В противном случае пользователь не может изменить позиций табуляции. Значение по умолчанию — `TRUE`.  
  
##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame  
 Указывает, имеет ли окно каждой вкладки плоский кадра.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton  
 Указывает, отображаются ли окно каждой вкладки **закрыть** кнопки.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, разделенном вкладку **закрыть** кнопку на правой стороне вкладки. В противном случае **закрыть** кнопка не отображается. Значение по умолчанию — `TRUE`.  
  
##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips  
 Указывает, отображаются ли всплывающие подсказки для вкладок.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, приложение отправляет `AFX_WM_ON_GET_TAB_TOOLTIP` сообщение главного фрейма. Это сообщение можно обрабатывать с помощью `ON_REGISTERED_MESSAGE` макрос.  
  
##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons  
 Указывает, следует ли отображать значки на вкладках MDI.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, значки отображаются на вкладках MDI. В противном случае значки не отображаются на вкладках. Значение по умолчанию — `FALSE`.  
  
##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize  
 Указывает размер границы в пикселях каждого окно вкладки.  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>Примечания  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) возвращает значение по умолчанию.  
  
##  <a name="m_style"></a>  CMDITabInfo::m_style  
 Задает стиль меток вкладок.  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>Примечания  
 Укажите одно из следующих стилей для меток вкладок.  
  
 `STYLE_3D`  
 Стиль объемных эффектов.  
  
 `STYLE_3D_ONENOTE`  
 Стиль Microsoft OneNote.  
  
 `STYLE_3D_VS2005`  
 Стиль Microsoft Visual Studio 2005.  
  
 `STYLE_3D_SCROLLED`  
 Стиль объемных эффектов с прямоугольник меток вкладок.  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 Плоский с общей горизонтальной полосы прокрутки.  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 Стиль объемных эффектов с метками round вкладки.  
  
##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation  
 Указывает, расположены ли метки вкладок в верхней или нижней части страницы.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Примечания  
 Применить к вкладкам один из следующих флагов расположение:  
  
-   LOCATION_BOTTOM: меток вкладок находятся в нижней части страницы.  
  
-   LOCATION_TOP: меток вкладок в верхней части страницы  
  
##  <a name="serialize"></a>  CMDITabInfo::Serialize  
 Читает или пишет этот объект из архива или в архив.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
 Объект [CArchive-класс](../../mfc/reference/carchive-class.md) объект для сериализации.  
  
## <a name="see-also"></a>См. также  
 [Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)   
 [Группы с вкладками MDI](../../mfc/mdi-tabbed-groups.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
