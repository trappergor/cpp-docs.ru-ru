---
title: Перетаскивание файлов в окне фрейма | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fc68923de531240a2d59336c79e54f6562b369c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380533"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Перетаскивание файлов в окне фрейма

Окна фрейма управляет связь с помощью проводника или диспетчера файлов.

Путем добавления нескольких инициализация вызывает в переопределении `CWinApp` функция-член `InitInstance`, как описано в [CWinApp: класс приложения](../mfc/cwinapp-the-application-class.md), может иметь фрейма окна косвенно открывать файлы, перетащить из файла Проводник или диспетчер файлов и удалить в окне фрейма. См. в разделе [перетаскивание диспетчера файлов](../mfc/special-cwinapp-services.md).

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)

