---
title: "Установка режима объекта CStatusBarCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CStatusBarCtrl
dev_langs: C++
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c954354321d814952ec3ac5ea148cc9177cd0fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Установка режима объекта CStatusBarCtrl
Существует два режима для `CStatusBarCtrl` объект: простые и непростые. В большинстве случаев в строке состояния будет иметь одну или несколько частей, и текст и возможно значок или значки. Это называется непростые режиме. Дополнительные сведения об этом режиме см. в разделе [инициализация частей объекта CStatusBarCtrl](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Тем не менее существуют случаи, когда вам требуется для отображения одной строки текста. В этом случае для потребностей достаточно простой режим. Чтобы изменить режим `CStatusBarCtrl` значение simple, следует вызвать [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) функции-члена. Как только строки состояния в простом режиме, задайте текст, вызвав **SetText** передача 255 в качестве значения для функции-члена **nPane** параметра.  
  
 Можно использовать [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) функции, чтобы определить, какой режим `CStatusBarCtrl` объект.  
  
> [!NOTE]
>  Объект строки состояние меняется с непростой простая или наоборот, немедленно перерисовке окна и, если применимо, автоматически восстанавливаются все определенные части.  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

