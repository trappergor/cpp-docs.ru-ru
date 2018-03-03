---
title: "Добавление функциональных возможностей в составной элемент управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dcf3ffa0c3168c2f96a3ad9bed13ab1213f63da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-functionality-to-the-composite-control"></a>Добавление функциональных возможностей в составной элемент управления
После добавления всех необходимых элементов управления в составной элемент управления, следующий шаг предполагает добавление новых функций. Эта особенность обычно разделяется на две категории:  
  
-   Поддержка дополнительных интерфейсов и настройки поведения элемента управления с дополнительные возможности, определенные.  
  
-   Обработка событий из автономной элемента управления ActiveX (или элементов управления).  
  
 Для цели и рамки данной статьи остальной части этого раздела посвящена исключительно обработка событий из элементов управления ActiveX.  
  
> [!NOTE]
>  Если необходимо обрабатывать сообщения от элементов управления Windows, см. раздел [реализация окна](../atl/implementing-a-window.md) Дополнительные сведения об обработке в ATL сообщений  
  
 После вставки элемента управления ActiveX в диалоговом окне ресурса, щелкните правой кнопкой мыши элемент управления и нажмите кнопку **добавить обработчик событий**. Выберите событие, для обработки и нажмите кнопку **добавлять и редактировать**. H-файл элемента управления будет добавлен код обработчика событий.  
  
 Точки подключения для элементов управления ActiveX в составной элемент управления автоматически подключаются и отключен путем вызова метода [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
## <a name="see-also"></a>См. также  
 [Принципы работы составного элемента управления](../atl/atl-composite-control-fundamentals.md)

