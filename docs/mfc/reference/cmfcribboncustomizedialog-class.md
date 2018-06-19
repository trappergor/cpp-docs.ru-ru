---
title: Класс CMFCRibbonCustomizeDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d195b2888c47a318369df13c371f85b21cc7bf84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370198"
---
# <a name="cmfcribboncustomizedialog-class"></a>Класс CMFCRibbonCustomizeDialog
Лента отображается **Настройка** страницы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Создает объект `CMFCRibbonCustomizeDialog`.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
## <a name="remarks"></a>Примечания  
 MFC автоматически создает этот класс не обработал сообщение AFX_WM_ON_RIBBON_CUSTOMIZE ли возвращают 0 из обработчика сообщений.  
  
 Если вы хотите использовать этот класс в приложении для отображения на ленте **Настройка** диалогового окна поле, просто создать его экземпляр и вызвать `DoModal` метод.  
  
 Поскольку этот класс является производным от [класса CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md), можно добавить пользовательские страницы с помощью `CMFCPropertySheet` API.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncustomizedialog.h  
  
##  <a name="cmfcribboncustomizedialog"></a>  CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 Создает объект `CMFCRibbonCustomizeDialog`.  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно (обычно главного фрейма).  
  
 [in] `pRibbon`  
 Указатель на `CMFCRibbonBar` , требуется настроить.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCRibbonCustomizeDialog` объекта.  
  
 [!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Создает экземпляр конструктора [CMFCRibbonCustomizePropertyPage класс](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) объекта и добавляет его в коллекцию страницы свойств.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
