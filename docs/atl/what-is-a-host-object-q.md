---
title: "Что такое объект узла? (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da735caa84c133b9cdf63fae5df8bdd3d5f774b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="what-is-a-host-object"></a>Что такое объект узла?
Объект узла является COM-объект, представляющий контейнер элемента управления ActiveX, предоставляемые ATL для конкретного окна. Узел объекта подклассов окном контейнера, чтобы может отражать сообщений для элемента управления, он предоставляет интерфейсы контейнера, необходимые для использования элементом управления, а также предоставляет [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) и [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) интерфейсы, чтобы можно было настроить среду управления.  
  
 Объект узла можно использовать для задания свойств внешнего контейнера.  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

