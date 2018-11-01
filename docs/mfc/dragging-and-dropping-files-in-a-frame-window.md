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
ms.openlocfilehash: 34fb6ec6d57bcf8bc1cf51a3ac0c0db5203b3ffa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498865"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Перетаскивание файлов в окне фрейма

Окна фрейма управляет связь с помощью проводника или диспетчера файлов.

Путем добавления нескольких инициализация вызывает в переопределении `CWinApp` функция-член `InitInstance`, как описано в [CWinApp: класс приложения](../mfc/cwinapp-the-application-class.md), может иметь фрейма окна косвенно открывать файлы, перетащить из файла Проводник или диспетчер файлов и удалить в окне фрейма. См. в разделе [перетаскивание диспетчера файлов](../mfc/special-cwinapp-services.md).

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)

