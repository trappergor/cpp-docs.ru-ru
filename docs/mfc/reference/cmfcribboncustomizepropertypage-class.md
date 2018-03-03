---
title: "Класс CMFCRibbonCustomizePropertyPage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ad58cb0b062e25a52742eec5491489d3744a9ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncustomizepropertypage-class"></a>Класс CMFCRibbonCustomizePropertyPage
Реализует настраиваемой страницы для **Настройка** диалоговое окно в приложениях на базе ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Создает объект `CMFCRibbonCustomizePropertyPage`.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Добавляет пользовательские категории для **команды** поле со списком.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Вызывается системой, когда пользователь щелкает **ОК** на **Настройка** диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Если вы хотите добавить собственные команды **Настройка** диалоговое окно, необходимо обработать сообщение AFX_WM_ON_RIBBON_CUSTOMIZE. В обработчик сообщений, создавать экземпляры `CMFCRibbonCustomizePropertyPage` объект в стеке. Создать список пользовательских команд, а затем вызвать `AddCustomCategory` Добавление новой страницы для **Настройка** диалоговое окно.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCRibbonCustomizePropertyPage` объекта и для добавления пользовательской категории.  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncustomizedialog.h  
  
##  <a name="addcustomcategory"></a>CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 Добавляет пользовательские категории для **команды** поле со списком.  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `lpszName`|Задает имя пользовательской категории.|  
|[in] `lstIDS`|Содержит идентификаторы команд ленты для отображения в пользовательской категории.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет категорию с именем `lpszName` для **команды** поле со списком. Когда пользователь выбирает категорию, команды, которые указаны в `lstIDS` отображаются в списке команд.  
  
##  <a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 Создает объект `CMFCRibbonCustomizePropertyPage`.  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRibbonBar`  
 Указатель на элемент управления ленты, для которой параметры для настройки.  
  
##  <a name="onok"></a>CMFCRibbonCustomizePropertyPage::OnOK  
 Calleld системой, когда пользователь щелкает **ОК** на **Настройка** диалоговое окно.  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию применяет параметры, выбранные в **Настройка** диалоговое окно «» на панель быстрого доступа.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
