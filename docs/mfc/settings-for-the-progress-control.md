---
title: "Параметры для управления ходом выполнения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ad62f3a60c8fe4fcd7efdde7f69f5c5e9450d14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-progress-control"></a>Параметры элемента управления "Индикатор выполнения"
Основные параметры управления хода выполнения ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) — это диапазон и текущее положение. Диапазон представляет всю продолжительность операции. Текущая позиция представляет ход выполнения приложения до завершения операции. Любые изменения диапазона или положение переводит элемент управления хода выполнения в перерисовывает себя.  
  
 По умолчанию имеет значение диапазона 0 - 100, а также начальное положение имеет значение 0. Чтобы получить текущие параметры диапазона для элемента управления хода выполнения, используйте [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) функции-члена. Чтобы изменить диапазон, используйте [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) функции-члена.  
  
 Чтобы установить позицию, используйте [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Получить текущую позицию без указания нового значения с помощью [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Например можно просто запросить состояние текущей операции.  
  
 Чтобы выполнить шаг текущую позицию элемента управления хода выполнения, используйте [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Чтобы задать объем каждого шага, используйте [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>См. также  
 [Использование CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

