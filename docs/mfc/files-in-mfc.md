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
ms.openlocfilehash: 815239b0d4de1938a810153cb98f39b2642b6e2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459336"
---
# <a name="files-in-mfc"></a>Файлы в MFC

В Microsoft Foundation Class Library (MFC), класса [CFile](../mfc/reference/cfile-class.md) обрабатывает обычные операции ввода-вывода. Этот сборник статей объясняется, как открывать и закрывать файлы, а также считывать и записывать данные в эти файлы. Здесь также рассматриваются состояние операции с файлами. Описание того, как использовать возможности объектно ориентированного сериализации MFC как альтернативный способ чтения и записи данных в файлах, см. в статье [сериализации](../mfc/serialization-in-mfc.md).

> [!NOTE]
>  При использовании MFC `CDocument` объектов, платформа выполняет большую часть работы сериализации автоматически. В частности, платформа создает и использует `CFile` объекта. Необходимо только написать код в переопределении `Serialize` функция-член класса `CDocument`.

`CFile` Класс предоставляет интерфейс для операций общего назначения двоичный файл. `CStdioFile` И `CMemFile` классы, производные от `CFile` и `CSharedFile` класс, производный от `CMemFile` укажите более специализированный файловых служб.

Дополнительные сведения о других способах работы с файлами MFC см. в разделе [обработка файлов](../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.

Сведения о производных `CFile` классов, см. в разделе [диаграммы иерархии MFC](../mfc/hierarchy-chart.md).

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

*Использовать CFile*

- [Открыть файл, имеющий CFile](../mfc/opening-files.md)

- [Чтение и запись в файл с CFile](../mfc/reading-and-writing-files.md)

- [Закройте файл с CFile](../mfc/closing-files.md)

- [Состояние доступа к файлу с CFile](../mfc/accessing-file-status.md)

*Использовать MFC сериализации (устойчивости объекта)*

- [Создание сериализуемого класса](../mfc/serialization-making-a-serializable-class.md)

- [Сериализация объекта с помощью объекта CArchive](../mfc/serialization-serializing-an-object.md)

- [Создать объект CArchive](../mfc/two-ways-to-create-a-carchive-object.md)

- [Использовать CArchive <\< и >> операторы](../mfc/using-the-carchive-output-and-input-operators.md)

- [Store и загрузка CObjects и объекты, производные от CObject через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[Класс CArchive](../mfc/reference/carchive-class.md)<br/>
[Класс CObject](../mfc/reference/cobject-class.md)
