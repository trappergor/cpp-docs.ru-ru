---
title: "Класс CMFCCustomColorsPropertyPage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage class
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fa534f22438b7be37e7893e545c3e060df69384f
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccustomcolorspropertypage-class"></a>Класс CMFCCustomColorsPropertyPage
Представляет страницы свойств, можно выбрать цвет в диалоговом окне цвет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCCustomColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Задает цвет компоненты на странице свойств.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCColorDialog` Класс использует этот класс для отображения страницы свойств пользовательского цвета. Дополнительные сведения о `CMFCColorDialog`, в разделе [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCCustomColorsPropertyPage` и задайте цвет компоненты на странице свойств.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#35;](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcustomcolorspropertypage.h  
  
##  <a name="setup"></a>CMFCCustomColorsPropertyPage::Setup  
 Задает цвет компоненты на странице свойств.  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `R`|Красный компонент RGB-значение.|  
|[in] `G`|Зеленый компонент значения RGB.|  
|[in] `B`|Синий компонент RGB-значение.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод обновляет текущий RGB и связанные HLS (оттенок, яркости и насыщенности) значение цвета страницы свойств. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) метод вызывает этот метод, когда платформа инициализирует диалоговое окно цвет или нажатии левой кнопки мыши. Дополнительные сведения о `CMFCColorDialog`, в разделе [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)   
 [Класс CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

