---
title: "Классы, связанные с OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4cb40e237eb6197dfe7e0cf944f12d25ca0e28e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-related-classes"></a>Классы, связанные с OLE
Эти классы предоставляют ряд различных служб, от исключения в файл ввода и вывода.  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 Используется для создания элементов при запросе от других контейнеров. Этот класс служит базовым классом для более конкретные типы фабрики, включая `COleTemplateServer`.  
  
 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 Используется для управления параллелизмом с OLE облегченного удаленной процедуры вызовов (LRPC).  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Использует COM `IStream` интерфейс для предоставления `CFile` доступ к составные файлы. Этот класс (производный от `CFile`) включает структурированное хранилище OLE MFC сериализации.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Чтобы разрешить перемещение, изменение размера и переукомплектации элементов на месте.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

