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
ms.openlocfilehash: 6c4b2b21bbfa19fb73997f8475cfa9a4047dc0ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371803"
---
# <a name="reading-and-writing-files"></a>Чтение и запись файлов

Если вы использовали функции обработки файлов c-времени, операции по чтению и записи MFC будут знакомы. Эта статья описывает чтение непосредственно от `CFile` объекта и написание его непосредственно. Вы также можете сделать буферизированный файл вв:/o с классом [CArchive.](../mfc/reference/carchive-class.md)

#### <a name="to-read-from-and-write-to-the-file"></a>Читать и писать в файл

1. Используйте `Read` `Write` функции и функции участника для чтения и записи данных в файле.

     -или-

1. Функция `Seek` участника также доступна для перехода к определенному смещению в файле.

`Read`принимает указатель на буфер и количество байтов для чтения и возвращает фактическое количество байтов, которые были прочитаны. Если необходимое количество байтов не может быть прочитано, поскольку конечный файл (EOF) достигнут, фактическое число байтов, прочитано, возвращается. При возникновении ошибки чтения выбрасывается исключение. `Write`похож на `Read`, но количество байтов написано не возвращается. Если происходит ошибка записи, включая ненаписание всех указанных байтов, выбрасывается исключение. Если у вас `CFile` есть действительный объект, вы можете прочитать из него или написать ему, как показано в следующем примере:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> Обычно следует выполнять операции ввода/вывода в блоке обработки исключений **try**/**catch.** Для получения дополнительной информации [см.](../mfc/exception-handling-in-mfc.md)

## <a name="see-also"></a>См. также раздел

[Файлы](../mfc/files-in-mfc.md)
