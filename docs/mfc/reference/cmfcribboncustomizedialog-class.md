---
title: "Класс CMFCRibbonCustomizeDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog class
- CMFCRibbonCustomizeDialog class, destructor
- ~CMFCRibbonCustomizeDialog destructor
- GetThisClass method
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d27247f89901adad1778313cdde6fe206a569f0d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncustomizedialog-class"></a>Класс CMFCRibbonCustomizeDialog
Лента отображается **Настройка** страницы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Создает объект `CMFCRibbonCustomizeDialog`.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
## <a name="remarks"></a>Примечания  
 MFC автоматически создает этот класс не обрабатывать сообщение AFX_WM_ON_RIBBON_CUSTOMIZE или возвращают 0 из обработчика сообщений.  
  
 Если вы хотите использовать этот класс в приложении для отображения на ленте **Настройка** диалоговом поле, просто создать его экземпляр и вызвать `DoModal` метод.  
  
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
  
##  <a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
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
 Указатель на `CMFCRibbonBar` , который будет настраиваться.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCRibbonCustomizeDialog` объекта.  
  
 [!code-cpp[NVC_MFC_RibbonApp&18;](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Конструктор создает [CMFCRibbonCustomizePropertyPage класс](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) объекта и добавляет его в коллекцию страницы свойств.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

