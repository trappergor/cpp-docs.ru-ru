---
title: Файлы в MFC
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
ms.openlocfilehash: 3a99c4143bbd27ba765b0289b80be8870a940f63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365314"
---
# <a name="files-in-mfc"></a>Файлы в MFC

В библиотеке класса Microsoft Foundation (MFC) [cFile](../mfc/reference/cfile-class.md) класса обрабатывает обычные операции ввоза/ввоза файлов. Это семейство статей объясняет, как открывать и закрывать файлы, а также читать и писать данные в эти файлы. В нем также рассматриваются операции со статусом файлов. Описание того, как использовать объектные функции сериализации MFC в качестве альтернативного способа чтения [Serialization](../mfc/serialization-in-mfc.md)и записи данных в файлах, см.

> [!NOTE]
> При использовании `CDocument` объектов MFC фреймворк выполняет большую часть работы по сериализации. В частности, фреймворк создает и использует `CFile` объект. Вам нужно только написать код в `Serialize` переопределение `CDocument`функции участника класса.

Класс `CFile` предоставляет интерфейс для операций двоичных файлов общего назначения. И `CStdioFile` `CMemFile` классы, `CFile` полученные `CSharedFile` из и `CMemFile` класса, полученных от поставки более специализированных файловых услуг.

Для получения дополнительной информации об альтернативах обработке *Run-Time Library Reference*файлов MFC [см.](../c-runtime-library/file-handling.md)

Для получения информации о [MFC hierarchy chart](../mfc/hierarchy-chart.md)полученных `CFile` классах см.

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

*Использование CFile*

- [Откройте файл с помощью CFile](../mfc/opening-files.md)

- [Читать и писать файл с CFile](../mfc/reading-and-writing-files.md)

- [Закрыть файл с помощью CFile](../mfc/closing-files.md)

- [Статус файла доступа с Помощью CFile](../mfc/accessing-file-status.md)

*Используйте сериализацию MFC (Объектная настойчивость)*

- [Создание серийного класса](../mfc/serialization-making-a-serializable-class.md)

- [Сериализация объекта через объект CArchive](../mfc/serialization-serializing-an-object.md)

- [Создание объекта CArchive](../mfc/two-ways-to-create-a-carchive-object.md)

- [Используйте <\< CArchive и операторов >> ](../mfc/using-the-carchive-output-and-input-operators.md)

- [Храните и загружают объекты CObjects и CObject через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>См. также раздел

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие темы МФЦ](../mfc/general-mfc-topics.md)<br/>
[Класс CArchive](../mfc/reference/carchive-class.md)<br/>
[Класс CObject](../mfc/reference/cobject-class.md)
