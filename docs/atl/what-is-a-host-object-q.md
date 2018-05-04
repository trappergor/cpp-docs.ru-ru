---
title: Что такое объект узла? (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d197f02949f6eaaeee50b428338684135d1db27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="what-is-a-host-object"></a>Что такое объект узла?
Объект узла является COM-объект, представляющий контейнер элемента управления ActiveX, предоставляемые ATL для конкретного окна. Узел объекта подклассов окном контейнера, чтобы может отражать сообщений для элемента управления, он предоставляет интерфейсы контейнера, необходимые для использования элементом управления, а также предоставляет [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) и [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) интерфейсы, чтобы можно было настроить среду управления.  
  
 Объект узла можно использовать для задания свойств внешнего контейнера.  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

