---
title: Управление текущим представлением
ms.date: 11/04/2016
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
ms.openlocfilehash: a926a9e31f7c43ab625220a4d759f6d536c2a77f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173344"
---
# <a name="managing-the-current-view"></a>Управление текущим представлением

В рамках реализации по умолчанию окна фрейма окна фрейма следит за текущему активному представлению. Если фрейм окна содержит несколько представлений, например в окне разделителя текущим представлением является самой последней представления используется. Активное представление не зависит от активного окна в Windows или текущий фокус ввода.

При изменении активного представления, а платформа уведомляет текущее представление, вызвав его [OnActivateView](../mfc/reference/cview-class.md#onactivateview) функция-член. Чтобы узнать, выполняется ли представление активируется или деактивируется путем проверки `OnActivateView` *bActivate* параметра. По умолчанию `OnActivateView` устанавливает фокус на текущее представление об активации. Можно переопределить `OnActivateView` для выполнения какой-либо специальные обработки при представлении деактивировать или повторно активированы. Например может потребоваться предоставить специальные визуальные отличия от других, неактивные представления активное представление.

Окна фрейма перенаправляет команды, чтобы его текущее представление (активная), как описано в разделе [маршрутизация команд](../mfc/command-routing.md), как часть стандартной маршрутизации команд.

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)
