---
title: Чтение и запись файлов
ms.date: 11/04/2016
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
ms.openlocfilehash: f68fd5c48bce214329437cc13fc39da0c3ca7d2b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228587"
---
# <a name="reading-and-writing-files"></a>Чтение и запись файлов

Если вы использовали функции обработки файлов библиотеки времени выполнения C, операции чтения и записи MFC будут отображаться знакомыми. В этой статье описывается чтение непосредственно из объекта и запись непосредственно в `CFile` объект. Также можно выполнять буферизованный файловый ввод-вывод с помощью класса [CArchive](../mfc/reference/carchive-class.md) .

#### <a name="to-read-from-and-write-to-the-file"></a>Чтение из файла и запись в него

1. Используйте `Read` `Write` функции элементов и для чтения и записи данных в файл.

     -или-

1. `Seek`Функция-член также доступна для перехода к определенному смещению в пределах файла.

`Read`принимает указатель на буфер и число байтов для чтения и возвращает фактическое число считанных байтов. Если требуемое число байтов не удалось считать из-за достижения конца файла (EOF), возвращается фактическое число байтов, считанных из памяти. При возникновении любой ошибки чтения возникает исключение. `Write`аналогичен `Read` , но число записанных байтов не возвращается. Если возникает ошибка записи, в том числе не запись всех указанных байтов, создается исключение. Если у вас есть допустимый `CFile` объект, можно выполнить чтение из него или записать в него, как показано в следующем примере:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> Обычно вы должны выполнять операции ввода-вывода в **`try`** / **`catch`** блоке обработки исключений. Дополнительные сведения см. в разделе [обработка исключений (MFC)](../mfc/exception-handling-in-mfc.md).

## <a name="see-also"></a>См. также статью

[Файлы](../mfc/files-in-mfc.md)
