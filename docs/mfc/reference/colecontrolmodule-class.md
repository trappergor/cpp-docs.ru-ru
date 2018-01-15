---
title: "Класс COleControlModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: OleControlModule
dev_langs: C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 196b69a0d86c3809415e030adb567c8642051f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colecontrolmodule-class"></a>Класс COleControlModule
Базовый класс, от которого необходимо наследовать объект модуля элемента управления OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет функции-члены для инициализации модуля управления. Каждый модуль управления OLE, который использует Microsoft Foundation classes может содержать только один объект, производный от `COleControlModule`. Этот объект создается в том случае, когда другие глобальные объекты C++ имеют иерархическую структуру. Объявите производного `COleControlModule` объекта на глобальном уровне.  
  
 Дополнительные сведения об использовании `COleControlModule` см. в описании [CWinApp](../../mfc/reference/cwinapp-class.md) класса и статья [элементы управления ActiveX](../../mfc/mfc-activex-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
## <a name="see-also"></a>См. также  
 [Пример MFC TESTHELP](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



