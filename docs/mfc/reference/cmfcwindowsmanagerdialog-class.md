---
title: "Класс CMFCWindowsManagerDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog class
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9f1508cfd3844fed413edd69063f1b3e64e80195
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcwindowsmanagerdialog-class"></a>Класс CMFCWindowsManagerDialog
`CMFCWindowsManagerDialog` Объектов позволяет пользователю управлять дочерними окнами MDI в приложении MDI.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Создает объект `CMFCWindowsManagerDialog`.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCWindowsManagerDialog` Содержит список дочерних MDI-окон, открытых в приложении. Пользователь вручную можно контролировать состояние дочерних MDI-окон в этом диалоговом окне.  
  
 `CMFCWindowsManagerDialog`встроенный [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md). `CMFCWindowsManagerDialog` Не является классом, который необходимо создать вручную. Вместо этого необходимо вызвать функцию [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), и он сможет создать и отобразить `CMFCWindowsManagerDialog` объекта.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCWindowsManagerDialog` путем вызова метода `CMDIFrameWndEx::ShowWindowsDialog`. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&18;](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxWindowsManagerDialog.h  
  
##  <a name="cmfcwindowsmanagerdialog"></a>CMFCWindowsManagerDialog::CMFCWindowsManagerDialog  
 Создает [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) объекта.  
  
```  
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,  
    BOOL bHelpButton = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMDIFrame`  
 Указатель на родительский или владелец окна.  
  
 [in] `bHelpButton`  
 Логический параметр, который указывает, отображаются ли платформа **помочь** кнопки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о диспетчеров визуального представления, в разделе [диспетчер визуализации](../../mfc/visualization-manager.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md)

