---
title: "Файл классов с вводом выводом | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.file
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 454e64d67321282030126d2aab023e9f587c1cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="file-io-classes"></a>Классов ввода-вывода файлов
Эти классы обеспечивают интерфейс традиционные дисковые файлы, файлы в памяти, активных потоков и сокеты Windows. Все классы, производные от `CFile` может использоваться с `CArchive` объекта для выполнения сериализации.  
  
 Используются следующие классы, особенно `CArchive` и `CFile`, при написании собственного обработки ввода вывода. Обычно необходимо наследование от этих классов. При использовании платформы приложений реализации по умолчанию **откройте** и **Сохранить** команды **файл** меню будет обрабатывать файлового ввода-вывода (с помощью класса `CArchive`), при условии, что переопределение документа `Serialize` функции для предоставления сведений о порядок сериализации его содержимое в документ. Дополнительные сведения о классах файла и сериализации см. в статье [файлы в MFC](../mfc/files-in-mfc.md) и статьи [сериализации](../mfc/serialization-in-mfc.md).  
  
 [CFile](../mfc/reference/cfile-class.md)  
 Предоставляет интерфейс файл двоичных файлов.  
  
 [CStdioFile](../mfc/reference/cstdiofile-class.md)  
 Предоставляет `CFile` интерфейс буферизованный поток в файлы на диске, обычно в текстовом режиме.  
  
 [CMemFile](../mfc/reference/cmemfile-class.md)  
 Предоставляет `CFile` интерфейс для файлов в памяти.  
  
 [CSharedFile](../mfc/reference/csharedfile-class.md)  
 Предоставляет `CFile` интерфейс для общих файлов в памяти.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Использует COM `IStream` интерфейс для предоставления `CFile` доступ к составные файлы.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Предоставляет `CFile` интерфейс Windows Socket.  
  
## <a name="related-classes"></a>Связанные классы  
 [CArchive](../mfc/reference/carchive-class.md)  
 Взаимодействует с `CFile` объекта для реализации постоянного хранилища для объектов с помощью сериализации (см. [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Исключение архива.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Исключение, ориентированного на файлы.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Предоставляет стандартное диалоговое окно открытия или сохранения файла.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Сохраняет последние использовавшиеся списка файлов (MRU).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

