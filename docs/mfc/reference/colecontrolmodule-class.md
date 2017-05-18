---
title: "Класс COleControlModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules
- MFC ActiveX controls, OLE control modules
- COleControlModule class
- control modules
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
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
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2e77c386875d25f47f0cc07eb3b7d315f1678c56
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolmodule-class"></a>Класс COleControlModule
Базовый класс, от которого необходимо наследовать объект модуля элемента управления OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет функции-члены для инициализации модуля управления. Каждый модуль управления OLE, который использует Microsoft Foundation classes может содержать только один объект, производный от `COleControlModule`. Этот объект создается при создании других глобальных объектов C++. Объявите производный `COleControlModule` объекта на глобальном уровне.  
  
 Дополнительные сведения об использовании `COleControlModule` см. в разделе [CWinApp](../../mfc/reference/cwinapp-class.md) класса и статью [элементы управления ActiveX](../../mfc/mfc-activex-controls.md).  
  
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




