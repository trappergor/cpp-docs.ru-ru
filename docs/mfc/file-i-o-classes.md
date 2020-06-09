---
title: Классы файлового ввода-вывода
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
ms.openlocfilehash: 2fcf4dfc1388df0df2bc25928ec8541486c6bb2d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615675"
---
# <a name="file-io-classes"></a>Классов ввода-вывода файлов

Эти классы предоставляют интерфейс для традиционных дисковых файлов, файлов в памяти, активных потоков и сокетов Windows. Все классы, производные от, `CFile` могут использоваться с `CArchive` объектом для выполнения сериализации.

Используйте следующие классы, в частности `CArchive` и `CFile` , при написании собственной обработки ввода-вывода. Обычно не требуется создавать производные от этих классов. При использовании платформы приложений реализации по умолчанию команд **открытия** и **сохранения** в меню **файл** будут выполнять обработку файлового ввода-вывода (с помощью класса `CArchive` ) при условии, что функция документа переопределяет, `Serialize` чтобы предоставить сведения о том, как документ сериализует свое содержимое. Дополнительные сведения о классах файлов и сериализации см. в файлах статей [в MFC](files-in-mfc.md) и в статье [сериализация](serialization-in-mfc.md).

[CFile](reference/cfile-class.md)<br/>
Предоставляет файловый интерфейс для двоичных файлов на диске.

[CStdioFile](reference/cstdiofile-class.md)<br/>
Предоставляет `CFile` интерфейс для буферизованного потокового потока файлов, обычно в текстовом режиме.

[CMemFile](reference/cmemfile-class.md)<br/>
Предоставляет `CFile` интерфейс для файлов в памяти.

[CSharedFile](reference/csharedfile-class.md)<br/>
Предоставляет `CFile` интерфейс для совместно используемых файлов в памяти.

[COleStreamFile](reference/colestreamfile-class.md)<br/>
Использует интерфейс COM `IStream` для предоставления `CFile` доступа к составным файлам.

[CSocketFile](reference/csocketfile-class.md)<br/>
Предоставляет `CFile` интерфейс для сокета Windows.

## <a name="related-classes"></a>Связанные классы

[CArchive](reference/carchive-class.md)<br/>
Взаимодействует с `CFile` объектом для реализации постоянного хранилища объектов с помощью сериализации (см. [CObject:: Serialize](reference/cobject-class.md#serialize)).

[CArchiveException](reference/carchiveexception-class.md)<br/>
Исключение архива.

[CFileException](reference/cfileexception-class.md)<br/>
Файловый объектно-ориентированное исключение.

[CFileDialog](reference/cfiledialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для открытия или сохранения файла.

[CRecentFileList](reference/crecentfilelist-class.md)<br/>
Сохраняет список последних использованных файлов (MRU).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
