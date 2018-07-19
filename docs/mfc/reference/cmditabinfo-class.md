---
title: Класс CMDITabInfo | Документация Майкрософт
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
ms.openlocfilehash: 37522cc2eaaa57abd5c3c7a0986532bb47d73f5e
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336459"
---
# <a name="cmditabinfo-class"></a>Класс CMDITabInfo
`CMDITabInfo` Класс используется для передачи параметров [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) метод. Задайте элементы этого класса, чтобы контролировать поведение групп вкладок MDI.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|Считывает этот объект из архива или записывает в него.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Указывает ли **закрыть** кнопка отображается на метке активной вкладки.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Указывает, следует ли цвета вкладок MDI.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Указывает, отображаются ли группу вкладок в контекстном меню, которая показывает список открытых документов или отображает кнопки прокрутки.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Указывает, можно ли пользователь менять положение вкладки путем перетаскивания.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Указывает, имеют ли вкладки неструктурированный кадра.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Указывает, отображает ли каждая метка вкладки **закрыть** кнопки.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Указывает, включены ли настраиваемые подсказки.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Указывает, следует ли отображать значки на вкладках MDI.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Указывает размер границы окна каждой вкладке.|  
|[CMDITabInfo::m_style](#m_style)|Задает стиль меток вкладок.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Указывает, расположены ли метки вкладки в верхней или нижней части страницы.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс задает параметры групп вкладок MDI, создаваемые платформой.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется задание значений разных переменных-членов в `CMDITabInfo` класса.  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton;  
 Указывает ли **закрыть** кнопка отображается на метке активной вкладки.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если метка активной вкладки будет отображать **закрыть** кнопки. **Закрыть** кнопка будет отсутствовать в правом верхнем углу области вкладок. В противном случае не будет отображена надпись активной вкладки **закрыть** кнопки. **Закрыть** кнопка будет отображаться в правом верхнем углу области вкладок.  
  
##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor  
 Указывает, имеет ли каждая вкладка MDI собственный цвет.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Примечания  
 Если значение равно TRUE, каждая вкладка будет иметь собственный цвет. Набор цветов, управляется библиотеки MFC. В противном случае вкладки отображаются белым цветом. Значение по умолчанию — FALSE.  
  
##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu  
 Указывает, отображаются ли каждая вкладка в контекстном меню, которое показывает список открытых документов на правом краю области вкладок.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если каждой вкладке windows отобразит всплывающее меню, которое показывает список открытых документов на правом краю области вкладок; В противном случае окно вкладка отображает кнопки прокрутки на правом краю области вкладок. Значение по умолчанию — FALSE.  
  
##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap  
 Указывает, можно ли пользователь менять положение вкладки путем перетаскивания.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если он может изменять позиции табуляции, перетащив на вкладках. В противном случае он не может изменить позиций табуляции. Значение по умолчанию — TRUE.  
  
##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame  
 Указывает, имеет ли каждое окно вкладки неструктурированный кадра.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton  
 Указывает, отображается ли в каждое окно вкладки **закрыть** кнопки.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если каждое окно вкладка отображает **закрыть** кнопку на правой стороне вкладки. В противном случае **закрыть** кнопка не отображается. Значение по умолчанию — TRUE.  
  
##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips  
 Указывает, отображаются ли всплывающие подсказки для вкладок.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если приложение отправляет сообщение AFX_WM_ON_GET_TAB_TOOLTIP главного фрейма. Это сообщение можно обработать с помощью on_registered_message-макрос.  
  
##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons  
 Указывает, следует ли отображать значки на вкладках MDI.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если значки отображаются на каждой вкладке MDI. В противном случае значков не отображаются на вкладках. Значение по умолчанию — FALSE.  
  
##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize  
 Размер границы в пикселях каждого окна вкладки.  
  
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
  
 STYLE_3D  
 Трехмерный стиль.  
  
 STYLE_3D_ONENOTE  
 Стиль Microsoft OneNote.  
  
 STYLE_3D_VS2005  
 Стиль Microsoft Visual Studio 2005.  
  
 STYLE_3D_SCROLLED  
 Трехмерный стиль с метками вкладку прямоугольника.  
  
 STYLE_FLAT_SHARED_HORZ_SCROLL  
 Плоское с общей горизонтальной полосы прокрутки.  
  
 STYLE_3D_ROUNDED_SCROLL  
 Трехмерный стиль с метками round вкладки.  
  
##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation  
 Указывает, расположены ли метки вкладки в верхней или нижней части страницы.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Примечания  
 Применяются к вкладкам один из следующих флагов расположение.  
  
-   LOCATION_BOTTOM: метки вкладки расположены в нижней части страницы.  
  
-   LOCATION_TOP: метки вкладки расположены в верхней части страницы  
  
##  <a name="serialize"></a>  CMDITabInfo::Serialize  
 Считывает или записывает этот объект из архива или в архив.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *ar*  
 Объект [класс CArchive](../../mfc/reference/carchive-class.md) объекта для сериализации.  
  
## <a name="see-also"></a>См. также  
 [Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)   
 [Группы с вкладками MDI](../../mfc/mdi-tabbed-groups.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
