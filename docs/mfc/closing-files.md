---
title: "Закрытие файлов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3833763394eda3ad64f1c72b80bee4d76785d5a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="closing-files"></a>Закрытие файлов
Как обычно в операциях ввода-вывода по завершении с файлом, его необходимо закрыть.  
  
#### <a name="to-close-a-file"></a>Чтобы закрыть файл  
  
1.  Используйте **закрыть** функции-члена. Эта функция закрывает файл файловой системы и при необходимости очищает буферы.  
  
 Если выделен [CFile](../mfc/reference/cfile-class.md) объект в кадре (как в примере, показанном в [открытие файлов](../mfc/opening-files.md)), объект будет автоматически закрыть и затем удаленных, когда он покидает область действия. Обратите внимание, что удаление `CFile` объекта не удаляет физический файл в файловой системе.  
  
## <a name="see-also"></a>См. также  
 [Файлы](../mfc/files-in-mfc.md)

