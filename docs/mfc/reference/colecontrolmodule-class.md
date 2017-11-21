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
ms.openlocfilehash: 0153adbae458d0f4ab432c2c7cb8c71621d76418
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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



