---
title: "Выбор графического объекта в контексте устройства | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5909625b816deb1303821aaec4034fa24f29be5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Выбор графического объекта в контексте устройства
Этот раздел относится к использованию графические объекты в контексте устройства окна. По окончании [создайте графический объект](../mfc/one-stage-and-two-stage-construction-of-objects.md), необходимо выбрать его в контекст устройства вместо объекта по умолчанию, хранящиеся в ней:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## <a name="lifetime-of-graphic-objects"></a>Время существования графические объекты  
 Графический объект, возвращаемый [SelectObject](../mfc/reference/cdc-class.md#selectobject) «временный». То есть, он будет удален при [OnIdle](../mfc/reference/cwinapp-class.md#onidle) функции-члена класса `CWinApp` времени при очередном программа получает простоя. Пока используется объект, возвращаемый `SelectObject` в одной функции без возвращения управления основной цикл обработки сообщений, будет иметь никаких проблем.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Графические объекты](../mfc/graphic-objects.md)  
  
-   [Одноэтапное и двухэтапное Создание графических объектов](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Контексты устройств](../mfc/device-contexts.md)  
  
-   [Рисование в представлении](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>См. также  
 [Графические объекты](../mfc/graphic-objects.md)

