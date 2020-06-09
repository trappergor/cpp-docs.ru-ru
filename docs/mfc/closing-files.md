---
title: Закрытие файлов
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 51e51c88260a51ec44f11ecb5c2a88e645194f4e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617235"
---
# <a name="closing-files"></a>Закрытие файлов

Как обычно в операциях ввода-вывода, после завершения работы с файлом его необходимо закрыть.

#### <a name="to-close-a-file"></a>Закрытие файла

1. Используйте функцию элемента **Close** . Эта функция закрывает файл файловой системы и очищает буфер при необходимости.

Если объект [кфиле](reference/cfile-class.md) был выделен в кадре (как показано в примере [открытия файлов](opening-files.md)), объект будет автоматически закрыт, а затем уничтожен при выходе из области действия. Обратите внимание, что удаление `CFile` объекта не приводит к удалению физического файла в файловой системе.

## <a name="see-also"></a>См. также раздел

[Файлы](files-in-mfc.md)
