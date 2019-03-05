---
title: Управление дочерними окнами MDI
ms.date: 11/19/2018
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: d4b4a4876f47452361b13837b0279f5bf98f8658
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283687"
---
# <a name="managing-mdi-child-windows"></a>Управление дочерними окнами MDI

MDI-окна главного фрейма (по одному для каждого приложения) содержат специальные дочернего окна вызывается mdiclient-окно. Mdiclient-окно управляет клиентской области окна главного фрейма и обслуживает дочерних окон: окна документов, производный от `CMDIChildWnd`. Так как окна документов, окон фреймов, сами (дочерних окон интерфейса MDI), они также могут иметь свои собственные дочерние элементы. Во всех этих случаях родительское окно управляет его дочерних окон и перенаправляет некоторые команды к ним.

В окне фрейма MDI фрейм окна управляет mdiclient-окно, изменить его расположение в сочетании с панели элементов управления. Mdiclient-окно, в свою очередь, управляет все дочерние MDI фрейма окна. На рисунке показана связь между окне фрейма MDI, его mdiclient-окно и его дочерних окон фрейма документа.

![Дочерние окна в окне фрейма MDI](../mfc/media/vc37gb1.gif "дочерние окна в окне фрейма MDI") <br/>
Windows фрейма MDI и дочерние элементы

Окне фрейма MDI также работает в сочетании с текущего дочернего окна MDI, если таковой имеется. Окно области MDI делегирует командных сообщений дочернюю MDI-ФОРМУ, прежде чем пытаться обрабатывать их сам.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)
