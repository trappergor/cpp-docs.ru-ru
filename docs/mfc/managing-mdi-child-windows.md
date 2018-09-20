---
title: Управление Windows дочерние MDI | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45989b7c07d27db1d7b2cda68751bd6165ee5382
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428282"
---
# <a name="managing-mdi-child-windows"></a>Управление дочерними окнами MDI

MDI-окна главного фрейма (по одному для каждого приложения) содержат специальные дочернего окна вызывается mdiclient-окно. Mdiclient-окно управляет клиентской области окна главного фрейма и обслуживает дочерних окон: окна документов, производный от `CMDIChildWnd`. Так как окна документов, окон фреймов, сами (дочерних окон интерфейса MDI), они также могут иметь свои собственные дочерние элементы. Во всех этих случаях родительское окно управляет его дочерних окон и перенаправляет некоторые команды к ним.

В окне фрейма MDI фрейм окна управляет mdiclient-окно, изменить его расположение в сочетании с панели элементов управления. Mdiclient-окно, в свою очередь, управляет все дочерние MDI фрейма окна. На рисунке показана связь между окне фрейма MDI, его mdiclient-окно и его дочерних окон фрейма документа.

![Дочерние окна в окне фрейма MDI](../mfc/media/vc37gb1.gif "vc37gb1") Windows фрейма MDI и дочерние элементы

Окне фрейма MDI также работает в сочетании с текущего дочернего окна MDI, если таковой имеется. Окно области MDI делегирует командных сообщений дочернюю MDI-ФОРМУ, прежде чем пытаться обрабатывать их сам.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)

