---
title: Перетаскивание файлов в окне фрейма
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
ms.openlocfilehash: 0129b939e0fe2afd5dd29623bb44418bfd16c20d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240664"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Перетаскивание файлов в окне фрейма

Окна фрейма управляет связь с помощью проводника или диспетчера файлов.

Путем добавления нескольких инициализация вызывает в переопределении `CWinApp` функция-член `InitInstance`, как описано в [CWinApp: Класс приложения](../mfc/cwinapp-the-application-class.md), вы можете косвенно открывать файлы из проводника или диспетчер файлов перетащен фрейм окна фрейма окна. См. в разделе [перетаскивание диспетчера файлов](../mfc/special-cwinapp-services.md).

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)
