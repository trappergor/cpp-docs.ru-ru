---
title: "Класс CMFCDesktopAlertWndButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton class
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 52294143c6caf5a8e0458c152540c41f7df78c57
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndbutton-class"></a>Класс CMFCDesktopAlertWndButton
Позволяет кнопки для добавления рабочего стола диалогового окна предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Конструктор по умолчанию.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Определяет, отображается ли кнопка в области заголовка диалогового окна предупреждения.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Определяет, является ли кнопки закрывает диалоговое окно предупреждения.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Логическое значение, указывающее, отображается ли кнопка в области заголовка диалогового окна предупреждения.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Логическое значение, указывающее, является ли кнопки закрывает диалоговое окно предупреждения.|  
  
### <a name="remarks"></a>Примечания  
 По умолчанию конструктор устанавливает `m_bIsCaptionButton` и `m_bIsCloseButton` данные-члены `FALSE`. Родительский `CMFCDesktopAlertDialog` набора объектов `m_bIsCaptionButton` для `TRUE` кнопку, находится в области заголовка диалогового окна предупреждения. `CMFCDesktopAlertDialog` Создает класс `CMFCDesktopAlertWndButton` объект, который служит в качестве кнопки, которая закрывает окно предупреждения поле и задает `m_bIsCloseButton` в `TRUE`.  
  
 Добавить `CMFCDesktopAlertWndButton` объектов `CMFCDesktopAlertDialog` объекта при добавлении любую кнопку. Дополнительные сведения о `CMFCDesktopAlertDialog`, в разделе [CMFCDesktopAlertDialog класса](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetImage` метод `CMFCDesktopAlertWndButton` класса. Этот фрагмент кода является частью [рабочего стола предупреждения демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#4;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo&#5;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton  
 Определяет, отображается ли кнопка в области заголовка диалогового окна предупреждения.  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данная кнопка отображается в области заголовка диалогового окна предупреждения; в противном случае — 0.  
  
##  <a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton  
 Определяет, является ли кнопки закрывает диалоговое окно предупреждения.  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопки закрывает диалоговое окно предупреждения; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

