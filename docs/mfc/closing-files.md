---
title: Закрытие файлов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97bd910ae4cb514cda07dd319f37a05a32712909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341030"
---
# <a name="closing-files"></a>Закрытие файлов
Как обычно в операциях ввода-вывода по завершении с файлом, его необходимо закрыть.  
  
#### <a name="to-close-a-file"></a>Чтобы закрыть файл  
  
1.  Используйте **закрыть** функции-члена. Эта функция закрывает файл файловой системы и при необходимости очищает буферы.  
  
 Если выделен [CFile](../mfc/reference/cfile-class.md) объект в кадре (как в примере, показанном в [открытие файлов](../mfc/opening-files.md)), объект будет автоматически закрыть и затем удаленных, когда он покидает область действия. Обратите внимание, что удаление `CFile` объекта не удаляет физический файл в файловой системе.  
  
## <a name="see-also"></a>См. также  
 [Файлы](../mfc/files-in-mfc.md)

