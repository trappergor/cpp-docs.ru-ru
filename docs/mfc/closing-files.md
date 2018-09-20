---
title: Закрытие файлов | Документация Майкрософт
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
ms.openlocfilehash: 9c392ef728e1d796a02cfa32edc2c3e8c74d083b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426241"
---
# <a name="closing-files"></a>Закрытие файлов

Как обычно в операциях ввода-вывода, после завершения работы с файлом, его необходимо закрыть.

#### <a name="to-close-a-file"></a>Чтобы закрыть файл

1. Используйте **закрыть** функция-член. Эта функция закрывает файл файловой системы и при необходимости очищает буферы.

Если выделен [CFile](../mfc/reference/cfile-class.md) объект в кадре (как в примере, показанном на [открытие файлов](../mfc/opening-files.md)), он будет автоматически закрыть и затем удаленных, когда оно выходит за пределы области. Обратите внимание, что удаление `CFile` объекта не удаляет физический файл в файловой системе.

## <a name="see-also"></a>См. также

[Файлы](../mfc/files-in-mfc.md)

