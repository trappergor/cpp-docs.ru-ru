---
title: "Перетаскивание файлов в окне фрейма | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 938640ed85e51d2b94b292bfe78a8d912b095188
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Перетаскивание файлов в окне фрейма
Окна фрейма управляет связь с помощью проводника или диспетчера файлов.  
  
 Путем добавления нескольких инициализация вызывает в переопределении `CWinApp` функции-члена `InitInstance`, как описано в [CWinApp: класс приложения](../mfc/cwinapp-the-application-class.md), может иметь фрейма окна косвенно открывать файлы, перетаскиваемые из файла Проводник или диспетчер файлов и удалить в окне фрейма. В разделе [перетаскивание диспетчера файлов](../mfc/special-cwinapp-services.md).  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

