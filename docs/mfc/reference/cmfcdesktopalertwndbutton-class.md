---
title: "Класс CMFCDesktopAlertWndButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs: C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae1153546851e6a34c14dacd33db04091de24557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdesktopalertwndbutton-class"></a>Класс CMFCDesktopAlertWndButton
Позволяет кнопки для добавления рабочего стола диалогового окна предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Конструктор по умолчанию.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Определяет, является ли данная кнопка отображается в области заголовка диалогового окна предупреждения.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Определяет, является ли кнопки закрывает диалоговое окно предупреждения.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|name|Описание:|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Логическое значение, указывающее, является ли данная кнопка отображается в области заголовка диалогового окна предупреждения.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Логическое значение, указывающее, является ли кнопки закрывает диалоговое окно предупреждения.|  
  
### <a name="remarks"></a>Примечания  
 По умолчанию конструктор устанавливает `m_bIsCaptionButton` и `m_bIsCloseButton` членов данных `FALSE`. Родительский `CMFCDesktopAlertDialog` набора объектов `m_bIsCaptionButton` для `TRUE` кнопки, находится в области заголовка диалогового окна предупреждения. `CMFCDesktopAlertDialog` Класс создает `CMFCDesktopAlertWndButton` объект, который служит в качестве кнопки, которая закрывает диалоговое окно предупреждения поле и задает `m_bIsCloseButton` для `TRUE`.  
  
 Добавить `CMFCDesktopAlertWndButton` объектов `CMFCDesktopAlertDialog` объекта при добавлении любую кнопку. Дополнительные сведения о `CMFCDesktopAlertDialog`, в разделе [CMFCDesktopAlertDialog класса](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetImage` метод `CMFCDesktopAlertWndButton` класса. Этот фрагмент кода является частью [Desktop предупреждения демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
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
 Определяет, является ли данная кнопка отображается в области заголовка диалогового окна предупреждения.  
  
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
 Ненулевое значение, если кнопке закрытия диалогового окна предупреждения; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
