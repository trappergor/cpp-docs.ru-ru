---
title: "Элементов управления ATL: Классы поддержки общих | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.atl.controls
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6164fc5cb25c724cf8999c3e6f3f2d71ade0589
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="controls-general-support-classes"></a>Элементы управления: Классы поддержки Общие
Следующие классы предоставляют общую поддержку для элементов управления ATL:  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) состоит из вспомогательные методы функции и данные, которые необходимы для элементов управления ATL.  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) предоставляет методы, необходимые для элементов управления.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) предоставляет основные методы, через которые контейнер связывается с элементом управления. Управляет активацией и деактивацией элементов управления на месте.  
  
-   [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) объединяет инициализации в один вызов, чтобы помочь избежать задержек при загрузке элементов управления контейнеров.  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) обеспечивает взаимодействие с минимальными мышью для элемента управления, в противном случае неактивные.  
  
## <a name="sample-program"></a>Пример программы  
 [ATLFire](../visual-cpp-samples.md)  
  
## <a name="related-articles"></a>Связанные статьи  
 [Учебник по ATL](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)

