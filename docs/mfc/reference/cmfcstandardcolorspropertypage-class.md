---
title: "Класс CMFCStandardColorsPropertyPage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fade2cc91d9681604fbd664419c693dde1527b84
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="cmfcstandardcolorspropertypage-class"></a>Класс CMFCStandardColorsPropertyPage
Представляет страницы свойств, пользователям возможность выбрать стандартные цвета в диалоговом окне цвет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCStandardColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCStandardColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCStandardColorsPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCColorDialog` Класс использует этот класс для отображения страницы свойств стандартный цвет. Дополнительные сведения о `CMFCColorDialog`, в разделе [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxstandardcolorspropertypage.h  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)   
 [Класс CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

