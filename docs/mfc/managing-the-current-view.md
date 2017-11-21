---
title: "Управление текущим представлением | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 339a3677783b789c6026dc0e46c09cfdb1d2e451
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="managing-the-current-view"></a>Управление текущим представлением
В рамках реализации по умолчанию для окна фрейма окна фрейма хранит информацию о активного представления. Если окно фрейма содержит более одного представления, как и для пример в окно-разделитель текущим представлением является самой последней представления используется. Активное представление не зависит от активного окна в Windows или текущий фокус ввода.  
  
 При изменении активного представления, а платформа сообщает текущее представление, вызвав его [OnActivateView](../mfc/reference/cview-class.md#onactivateview) функции-члена. Чтобы узнать, выполняется ли представление активируется или деактивируется путем проверки `OnActivateView` `bActivate` параметр. По умолчанию `OnActivateView` устанавливает фокус в текущее представление об активации. Можно переопределить `OnActivateView` выполнять любой специальную обработку при представлении деактивировать или повторно активированы. Например может потребоваться предоставить специальные визуальные подсказки, чтобы отличить от других, неактивные представления активное представление.  
  
 Окна фрейма перенаправляет команды, чтобы его текущее представление (активная), как описано в [маршрутизация команд](../mfc/command-routing.md), в рамках стандартной маршрутизации команд.  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

