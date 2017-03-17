---
title: "Класс CMDITabInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMDITabInfo class
- CMDITabInfo class, constructor
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
caps.latest.revision: 37
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
ms.openlocfilehash: a45532c98d5da7d89d27e3d29d9b40075cf0376f
ms.lasthandoff: 02/24/2017

---
# <a name="cmditabinfo-class"></a>Класс CMDITabInfo
`CMDITabInfo` Класс используется для передачи параметров для [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) метод. Задайте элементы этого класса, чтобы контролировать поведение групп вкладок MDI.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|Считывает этот объект из архива или записывает в него.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Указывает ли **закрыть** кнопка отображается на метке активной вкладки.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Задает цвет вкладок MDI.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Указывает, отображаются ли в группу вкладок всплывающего меню, которое показывает список открытых документов или отображает кнопки прокрутки.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Указывает ли пользователь можно переключить положения вкладки путем перетаскивания.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Указывает, имеют ли вкладки плоский кадра.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Указывает, отображаются ли каждая вкладка метка **закрыть** кнопки.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Указывает, включены ли настраиваемые всплывающие подсказки.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Указывает необходимость отображения значков на вкладках окна MDI.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Указывает размер границы каждого окна вкладки.|  
|[CMDITabInfo::m_style](#m_style)|Задает стиль метки вкладок.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Указывает, находятся ли метки вкладок в верхней или нижней части страницы.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс задает параметры групп вкладок MDI, которые платформа создает.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как устанавливать значения различных переменных-членов в `CMDITabInfo` класса.  
  
 [!code-cpp[NVC_MFC_MDITab&#1;](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>CMDITabInfo::m_bActiveTabCloseButton;  
 Указывает ли **закрыть** кнопка отображается на метке активной вкладки.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, будет отображена надпись активной вкладке **закрыть** кнопки. **Закрыть** будут удалены кнопки в правом верхнем углу области вкладки. В противном случае — не будет отображаться метка активной вкладке **закрыть** кнопки. **Закрыть** кнопка отображается в правом верхнем углу области вкладки.  
  
##  <a name="m_bautocolor"></a>CMDITabInfo::m_bAutoColor  
 Указывает, имеет ли каждая вкладка MDI собственный цвет.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, каждая вкладка будет иметь свой собственный цвет. Набор цветов, осуществляется библиотекой MFC. В противном случае — в техническом отображаются вкладки. Значение по умолчанию — `FALSE`.  
  
##  <a name="m_bdocumentmenu"></a>CMDITabInfo::m_bDocumentMenu  
 Указывает, отображается ли каждая вкладка всплывающее меню, которое показывает список открытых документов по правому краю области вкладки.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, windows Каждая вкладка отображает всплывающее меню, содержащее список открытых документов по правому краю области вкладки. В противном случае — окно вкладка отображает кнопки прокрутки по правому краю области вкладки. Значение по умолчанию — `FALSE`.  
  
##  <a name="m_benabletabswap"></a>CMDITabInfo::m_bEnableTabSwap  
 Указывает ли пользователь можно переключить положения вкладки путем перетаскивания.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, пользователь может изменить позиции табуляции, перетащив на вкладках. В противном случае — пользователь не может изменить позиции табуляции. Значение по умолчанию — `TRUE`.  
  
##  <a name="m_bflatframe"></a>CMDITabInfo::m_bFlatFrame  
 Указывает, имеет ли окно каждой вкладки плоский кадра.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>CMDITabInfo::m_bTabCloseButton  
 Указывает, отображаются ли каждое окно вкладку **закрыть** кнопки.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, каждая вкладка окно отображает **закрыть** кнопку на правой стороне вкладки. В противном случае — **закрыть** кнопка не отображается. Значение по умолчанию — `TRUE`.  
  
##  <a name="m_btabcustomtooltips"></a>CMDITabInfo::m_bTabCustomTooltips  
 Отображение вкладок подсказки.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, приложение отправляет `AFX_WM_ON_GET_TAB_TOOLTIP` сообщение главного фрейма. Это сообщение можно обработать с помощью `ON_REGISTERED_MESSAGE` макрос.  
  
##  <a name="m_btabicons"></a>CMDITabInfo::m_bTabIcons  
 Указывает необходимость отображения значков на вкладках окна MDI.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, значки отображаются на каждой вкладке MDI. В противном случае — значков не отображаются на вкладках. Значение по умолчанию — `FALSE`.  
  
##  <a name="m_ntabbordersize"></a>CMDITabInfo::m_nTabBorderSize  
 Указывает размер границы в пикселях каждого окна вкладки.  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>Примечания  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) возвращает значение по умолчанию.  
  
##  <a name="m_style"></a>CMDITabInfo::m_style  
 Задает стиль метки вкладок.  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>Примечания  
 Укажите один из следующих стилей для корешков:  
  
 `STYLE_3D`  
 Трехмерный стиль.  
  
 `STYLE_3D_ONENOTE`  
 Стиль Microsoft OneNote.  
  
 `STYLE_3D_VS2005`  
 Стиль Microsoft Visual Studio 2005.  
  
 `STYLE_3D_SCROLLED`  
 Трехмерный стиль с метками вкладку прямоугольника.  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 Плоский с общей горизонтальной полосы прокрутки.  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 Трехмерный стиль с метками round вкладки.  
  
##  <a name="m_tablocation"></a>CMDITabInfo::m_tabLocation  
 Указывает, находятся ли метки вкладок в верхней или нижней части страницы.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Примечания  
 Применить к вкладкам один из флагов расположение:  
  
-   LOCATION_BOTTOM: метки вкладки расположены в нижней части страницы.  
  
-   LOCATION_TOP: метки вкладок в верхней части страницы  
  
##  <a name="serialize"></a>CMDITabInfo::Serialize  
 Считывает или записывает этот объект из архива или в архив.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
 Объект [CArchive-класс](../../mfc/reference/carchive-class.md) объекта для сериализации.  
  
## <a name="see-also"></a>См. также  
 [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md)   
 [Группы с вкладками MDI](../../mfc/mdi-tabbed-groups.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

