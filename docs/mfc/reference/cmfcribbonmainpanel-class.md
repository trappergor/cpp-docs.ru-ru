---
title: "Класс CMFCRibbonMainPanel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel class
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3fc37a953e62e6ea90de8402b7f2912b06967e13
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonmainpanel-class"></a>Класс CMFCRibbonMainPanel
Реализует панель ленты, которое отображается при нажатии кнопки [cmfcribbonapplicationbutton –](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Конструктор по умолчанию.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|Добавляет элемент ленты в левой части панели кнопку приложения. (Переопределяет [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Добавляет текстовую строку меню списка последних файлов.|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Добавляет элемент ленты в нижней части панели приложения ленты.|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Добавляет элемент ленты в правой области окна приложения панель кнопок.|  
|`CMFCRibbonMainPanel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Возвращает прямоугольник, представляющий область главной панели ленты.|  
|`CMFCRibbonMainPanel::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
## <a name="remarks"></a>Примечания  
 Отображает платформу `CMFCRibbonMainPanel` при открытии панели приложения. Он содержит три панели:  
  
-   Левая панель содержит команды, связанные с файлами, такие как **откройте**, **Сохранить**, **печати**, и **закрыть**. Чтобы добавить команду в эту область, вызовите [CMFCRibbonMainPanel::Add](#add).  
  
-   Правая панель содержит параметры, которые изменяют команды, щелкните в левой панели. Например, если щелкнуть **Сохранить как** в левой области справа отображаются доступные типы файлов. Чтобы добавить элемент в эту область, вызовите [CMFCRibbonMainPanel::AddToRight](#addtoright).  
  
-   На нижней панели содержит кнопки, которые позволяют изменить параметры приложения и выйти из программы. Чтобы добавить элемент в эту область, вызовите [CMFCRibbonMainPanel::AddToBottom](#addtobottom).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonMainPanel.h  
  
##  <a name="add"></a>CMFCRibbonMainPanel::Add  
 Добавляет элемент ленты в левой части панели кнопку приложения.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pElem`  
 Указатель на элемент Добавление главной панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Добавляет элемент ленты, панель. Элементы, добавленные с помощью этого метода будет находиться в левом столбце главной панели.  
  
##  <a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList  
 Добавляет текстовую строку меню списка последних файлов.  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszLabel`  
 Указывает строку, чтобы добавить в список последних файлов.  
  
 `nWidth`  
 Ширина в пикселях панели списка последних файлов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addtobottom"></a>CMFCRibbonMainPanel::AddToBottom  
 Добавляет элемент ленты в нижней части панели приложения ленты.  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pElem`  
 Указатель на элемент ленты, добавление в нижней части главной панели.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addtoright"></a>CMFCRibbonMainPanel::AddToRight  
 Добавляет элемент ленты в правой области окна приложения панель кнопок.  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Параметры  
 `pElem`  
 Указатель на элемент ленты для добавления в правой части главной панели.  
  
 `nWidth`  
 Ширина в пикселях правой панели.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для добавления элемента ленты на правой панели. Правая панель обычно отображает список последних файлов, но можно добавить любые другие ribbon элемент здесь.  
  
##  <a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame  
 Возвращает прямоугольник, представляющий область главной панели ленты.  
  
```  
CRect GetCommandsFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, представляющий область главной панели ленты.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

