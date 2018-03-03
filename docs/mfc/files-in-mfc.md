---
title: "Файлы в MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d2cd6344f11a9c32ade0fc3241225a8763c18b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="files-in-mfc"></a>Файлы в MFC
В Microsoft Foundation Class библиотеки (MFC), класс [CFile](../mfc/reference/cfile-class.md) обрабатывает обычных операций ввода-вывода. Этот сборник статей объясняется, как для открытия и закрытия файлов, а также читать и записывать данные в эти файлы. В нем также описывается состояние операции с файлами. Описание способов использования возможности сериализации на основе объектов MFC как альтернативный способ чтения и записи данных в файлах, см. в статье [сериализации](../mfc/serialization-in-mfc.md).  
  
> [!NOTE]
>  При использовании MFC **CDocument** объектов платформа выполняет большую часть работы сериализации автоматически. В частности, платформа создает и использует `CFile` объекта. Необходимо написать код в переопределении `Serialize` функции-члена класса **CDocument**.  
  
 `CFile` Класс предоставляет интерфейс для операций общего назначения двоичный файл. `CStdioFile` И `CMemFile` классы, производные от `CFile` и `CSharedFile` класс, производный от `CMemFile` предоставить более специализированные файловых служб.  
  
 Дополнительные сведения о других способах работы с файлами MFC см. в разделе [обработка файлов](../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.  
  
 Сведения о производных `CFile` классы, в разделе [диаграммы иерархии MFC](../mfc/hierarchy-chart.md).  
  
## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать  
 *Используйте CFile*  
  
-   [Откройте файл с CFile](../mfc/opening-files.md)  
  
-   [Чтение и запись в файл с CFile](../mfc/reading-and-writing-files.md)  
  
-   [Закройте файл с CFile](../mfc/closing-files.md)  
  
-   [Состояние доступа к файлу с CFile](../mfc/accessing-file-status.md)  
  
 *Использование MFC сериализации (сохранения объектов)*  
  
-   [Создание сериализуемого класса](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Сериализовать объект с помощью объекта CArchive](../mfc/serialization-serializing-an-object.md)  
  
-   [Создать объект CArchive](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [Используйте CArchive <\< и >> операторы](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [Хранить и загрузка CObjects и объекты, производные от CObject через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [CArchive-класс](../mfc/reference/carchive-class.md)   
 [Класс CObject](../mfc/reference/cobject-class.md)
