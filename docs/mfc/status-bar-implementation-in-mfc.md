---
title: "Реализация строки состояния в MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COldStatusBar
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d81982e23f100fe75d6cc5769cd19359bfaa6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="status-bar-implementation-in-mfc"></a>Реализация строки состояния в MFC
Объект [CStatusBar](../mfc/reference/cstatusbar-class.md) объект является панель элементов управления со строкой панелей вывода текста. Панелей вывода используются строки сообщения, а индикаторы состояния. Примеры включают справочное сообщение строки меню, которые кратко объясните команду меню и индикаторы, которые показывают состояние SCROLL LOCK, NUM LOCK и другие ключи.  
  
 Начиная с MFC версии 4.0, строки состояния реализуются с помощью класса [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), который инкапсулирует стандартного элемента управления в строке состояния. Для обеспечения обратной совместимости MFC сохраняет старые реализация строки состояния в классе **COldStatusBar**. Документация для предыдущих версий MFC описывает **COldStatusBar** под `CStatusBar`.  
  
 [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), функция-член новые 4.0 MFC позволяет воспользоваться преимуществами общих элементов управления Windows поддержка строки дополнительные функциональные возможности и настройки состояния. `CStatusBar`функции-члены обеспечивают большую часть функций общих элементов управления Windows; Тем не менее, при вызове `GetStatusBarCtrl`, можно дать вашей строки состояния даже несколько характеристик строки состояния. При вызове `GetStatusBarCtrl`, он возвращает ссылку на `CStatusBarCtrl` объекта. Можно использовать эту ссылку для управления строки состояния.  
  
 На следующем рисунке показана строка состояния, отображаются несколько индикаторы.  
  
 ![Строка состояния](../mfc/media/vc37dy1.gif "vc37dy1")  
Строка состояния  
  
 Как панели инструментов объект строки состояния внедряется в его родительский фрейм окна и будет создан автоматически при создании окна фрейма. Строка состояния, как и все панели элементов управления, будет удален автоматически, а также при уничтожении родительского фрейма.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Обновление текса на панели строки состояния](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   Классы MFC [CStatusBar](../mfc/reference/cstatusbar-class.md) и [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [Панели элементов управления](../mfc/control-bars.md)  
  
-   [Диалоговые панели](../mfc/dialog-bars.md)  
  
-   [Панели инструментов (реализация панели инструментов MFC)](../mfc/mfc-toolbar-implementation.md)  
  
## <a name="see-also"></a>См. также  
 [Строки состояния](../mfc/status-bars.md)

