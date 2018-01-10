---
title: "Класс CMFCRibbonMainPanel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8b5508abdc90c4c566d078f2f75c30822c7a18e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonmainpanel-class"></a>Класс CMFCRibbonMainPanel
Реализует панель ленты, который отображается при нажатии кнопки [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Конструктор по умолчанию.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|Добавляет элемент ленты в левой части панели кнопку приложения. (Переопределяет [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Добавляет текстовую строку в меню списка последних файлов.|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Добавляет элемент ленты в нижней части панели ленты приложения.|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Добавляет элемент ленты справа панель кнопок приложения.|  
|`CMFCRibbonMainPanel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Возвращает прямоугольник, представляющий область главной панели ленты.|  
|`CMFCRibbonMainPanel::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
## <a name="remarks"></a>Примечания  
 Платформа отображает `CMFCRibbonMainPanel` при открытии панели приложения. Он содержит три панели:  
  
-   Левая панель содержит команды, связанные с файлами, такие как **откройте**, **Сохранить**, **печати**, и **закрыть**. Чтобы добавить команду на эту панель, вызовите [CMFCRibbonMainPanel::Add](#add).  
  
-   Правая панель содержит параметры, которые изменяют команды, щелкните в левой области. Например, если щелкнуть **Сохранить как** на левой панели правой панели можно отобразить типов данных. Чтобы добавить элемент в этой области, вызовите [CMFCRibbonMainPanel::AddToRight](#addtoright).  
  
-   На нижней панели содержит кнопки, которые позволяют изменить параметры приложения и выйти из программы. Чтобы добавить элемент в этой области, вызовите [CMFCRibbonMainPanel::AddToBottom](#addtobottom).  
  
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
 Указатель на элемент ленты для добавления к главной панели.  
  
### <a name="remarks"></a>Примечания  
 Добавляет элемент ленты на панель. Элементы, добавленные с помощью этого метода будет находиться в левом столбце главной панели.  
  
##  <a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList  
 Добавляет текстовую строку в меню списка последних файлов.  
  
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
 Добавляет элемент ленты в нижней части панели ленты приложения.  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pElem`  
 Указатель на элемент ленты, добавление в нижней части главной панели.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addtoright"></a>CMFCRibbonMainPanel::AddToRight  
 Добавляет элемент ленты справа панель кнопок приложения.  
  
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
 Эта функция добавьте элемент ленты в правой панели. Правая панель обычно отображает список последних файлов, но можно добавить любые другие элемента ленты здесь.  
  
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
