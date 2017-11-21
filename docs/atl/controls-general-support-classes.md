---
title: "Элементов управления ATL: Классы поддержки общих | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.controls
dev_langs: C++
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5d969481874762c5eefeb805d954ffad6114033e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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

