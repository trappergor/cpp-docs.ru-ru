---
title: Управление текущим представлением | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09d29f4bc0b62e5824209759d45e63c1d9e2daa6
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928744"
---
# <a name="managing-the-current-view"></a>Управление текущим представлением
В рамках реализации по умолчанию для окна фрейма окна фрейма хранит информацию о активного представления. Если окно фрейма содержит более одного представления, как и для пример в окно-разделитель текущим представлением является самой последней представления используется. Активное представление не зависит от активного окна в Windows или текущий фокус ввода.  
  
 При изменении активного представления, а платформа сообщает текущее представление, вызвав его [OnActivateView](../mfc/reference/cview-class.md#onactivateview) функции-члена. Чтобы узнать, выполняется ли представление активируется или деактивируется путем проверки `OnActivateView` *bActivate* параметр. По умолчанию `OnActivateView` устанавливает фокус в текущее представление об активации. Можно переопределить `OnActivateView` выполнять любой специальную обработку при представлении деактивировать или повторно активированы. Например может потребоваться предоставить специальные визуальные подсказки, чтобы отличить от других, неактивные представления активное представление.  
  
 Окна фрейма перенаправляет команды, чтобы его текущее представление (активная), как описано в [маршрутизация команд](../mfc/command-routing.md), в рамках стандартной маршрутизации команд.  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

