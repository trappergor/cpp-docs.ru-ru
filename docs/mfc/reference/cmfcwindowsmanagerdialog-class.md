---
title: "Класс CMFCWindowsManagerDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs: C++
helpviewer_keywords: CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f20a93135a6f310b626cbe12f68f72c64e4ce8e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcwindowsmanagerdialog-class"></a>Класс CMFCWindowsManagerDialog
`CMFCWindowsManagerDialog` Объектов позволяет пользователю управлять дочерними окнами MDI в приложении MDI.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Создает объект `CMFCWindowsManagerDialog`.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCWindowsManagerDialog` Содержит список дочерних MDI-окон, которые в настоящее время открыты в приложении. Пользователь вручную можно контролировать состояние дочерних MDI-окон в этом диалоговом окне.  
  
 `CMFCWindowsManagerDialog`встроенный [класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md). `CMFCWindowsManagerDialog` Не является классом, который необходимо создать вручную. Вместо этого вызовите функцию [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), и он будет создавать и отображать `CMFCWindowsManagerDialog` объекта.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCWindowsManagerDialog` путем вызова метода `CMDIFrameWndEx::ShowWindowsDialog`. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
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
 Указатель на окно родительского или владельца.  
  
 [in] `bHelpButton`  
 Логический параметр, указывает, отображаются ли платформа **справки** кнопки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о диспетчерах visual см [диспетчер визуализации](../../mfc/visualization-manager.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)
