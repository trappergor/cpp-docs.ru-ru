---
title: Класс CMFCRibbonCustomizePropertyPage | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bb2f799dedd11ed1c8e0e909e7a5b1dcbb7adc5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707512"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>Класс CMFCRibbonCustomizePropertyPage
Реализует пользовательскую страницу для **Настройка** диалоговое окно в приложениях, основанных на Ribbon.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Создает объект `CMFCRibbonCustomizePropertyPage`.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Добавляет пользовательскую категорию для **команды** поле со списком.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Вызывается системой, когда пользователь щелкает **ОК** на **Настройка** диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Если вы хотите добавить пользовательские команды **Настройка** диалоговом окне необходимо обрабатывать сообщения AFX_WM_ON_RIBBON_CUSTOMIZE. В обработчике сообщений, создать экземпляр `CMFCRibbonCustomizePropertyPage` объект в стеке. Создать список пользовательских команд, а затем вызвать `AddCustomCategory` для добавления новой страницы, **Настройка** диалоговое окно.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется создание `CMFCRibbonCustomizePropertyPage` объекта и добавления пользовательской категории.  
  
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
  
##  <a name="addcustomcategory"></a>  CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 Добавляет пользовательскую категорию для **команды** поле со списком.  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|*lpszName*|[in] Задает имя пользовательской категории.|  
|*lstIDS*|[in] Содержит идентификаторы команд ленты для отображения в пользовательской категории.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет категорию с именем *lpszName* для **команды** поле со списком. Когда пользователь выбирает категорию, команды, которые указаны в *lstIDS* отображаются в списке команд.  
  
##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 Создает объект `CMFCRibbonCustomizePropertyPage`.  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
*pRibbonBar*<br/>
[in] Указатель на элемент управления ленты, для которого параметры для настройки.  
  
##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK  
 Calleld системой, когда пользователь щелкает **ОК** на **Настройка** диалоговое окно.  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию применяет параметры, выбранные в **Настройка** диалоговое окно в панель быстрого доступа.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
