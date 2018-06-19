---
title: Класс CMFCCustomColorsPropertyPage | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c02c2590e4143460a2cd89bb2b7e7e167c92c0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370813"
---
# <a name="cmfccustomcolorspropertypage-class"></a>Класс CMFCCustomColorsPropertyPage
Представляет страницы свойств, можно выбрать пользовательские цвета в диалоговом окне цвет.  
  
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
|`CMFCCustomColorsPropertyPage::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Задает цвет компоненты на странице свойств.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCColorDialog` Использует этот класс для отображения страницы свойств пользовательский цвет. Дополнительные сведения о `CMFCColorDialog`, в разделе [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCCustomColorsPropertyPage` и задайте для его компонентов цвета страницы свойств.  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcustomcolorspropertypage.h  
  
##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup  
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
|[in] `R`|RGB-значение красного компонента.|  
|[in] `G`|Зеленый компонент значения RGB.|  
|[in] `B`|Синий компонент RGB-значение.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод обновляет текущее RGB и связанные HLS (оттенок, светлые и насыщенность) цвет значения страницы свойств. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) метод вызывает этот метод, когда платформа инициализирует диалоговое окно «цвет» или нажатии левой кнопки мыши. Дополнительные сведения о `CMFCColorDialog`, в разделе [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)   
 [Класс CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
