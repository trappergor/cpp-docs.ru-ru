---
title: Классов ввода вывода файлов
ms.date: 11/04/2016
f1_keywords:
- vc.classes.file
helpviewer_keywords:
- disk file classes [MFC]
- stdio classes [MFC]
- OLE streams [MFC]
- I/O [MFC], MFC classes
- translated stream classes [MFC]
- file I/O classes [MFC]
- I/O [MFC], classes
- sockets classes [MFC]
- stream classes [MFC]
- memory file classes [MFC]
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
ms.openlocfilehash: 914325ec56f0cae30c7293305496d65f358f2731
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281659"
---
# <a name="file-io-classes"></a>Классов ввода-вывода файлов

Эти классы предоставляют интерфейс для традиционных дисковых файлов, файлов в памяти, активных потоков и сокеты Windows. Все классы, производные от `CFile` может использоваться с `CArchive` объект для выполнения сериализации.

Используются следующие классы, особенно `CArchive` и `CFile`, при написании собственных обработки ввода вывода. Обычно вы не обязательно должны быть производным от этих классов. Если вы используете платформу приложения, реализация по умолчанию **откройте** и **Сохранить** команд на **файл** меню будет обрабатывать файлового ввода-вывода (с помощью класса `CArchive`), до тех пор, пока переопределить документа `Serialize` функции для предоставления сведений о как документ сериализует его содержимое. Дополнительные сведения о классах файла и сериализации см. в статье [файлы в MFC](../mfc/files-in-mfc.md) и статью [сериализации](../mfc/serialization-in-mfc.md).

[CFile](../mfc/reference/cfile-class.md)<br/>
Предоставляет интерфейс файл двоичных файлов.

[CStdioFile](../mfc/reference/cstdiofile-class.md)<br/>
Предоставляет `CFile` интерфейс буферизованного потока файлов, обычно в текстовом режиме.

[CMemFile](../mfc/reference/cmemfile-class.md)<br/>
Предоставляет `CFile` интерфейс к файлам в памяти.

[CSharedFile](../mfc/reference/csharedfile-class.md)<br/>
Предоставляет `CFile` интерфейс к общим файлам в памяти.

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
Использует COM `IStream` интерфейс, чтобы предоставить `CFile` доступ к составные файлы.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Предоставляет `CFile` интерфейс сокетов Windows.

## <a name="related-classes"></a>Связанные классы

[CArchive](../mfc/reference/carchive-class.md)<br/>
Взаимодействует с `CFile` объекту реализовать постоянное хранилище объектов с помощью сериализации (см. в разделе [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
Исключение архива.

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
Исключение, ориентированные на файлы.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
Предоставляет стандартное диалоговое окно открытия или сохранения файла.

[CRecentFileList](../mfc/reference/crecentfilelist-class.md)<br/>
Поддерживает наиболее часто используемое список файлов (MRU).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
