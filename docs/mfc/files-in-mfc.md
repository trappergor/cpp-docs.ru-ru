---
title: "Файлы в MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "двоичный доступ"
  - "двоичный доступ, операции с двоичными файлами в MFC"
  - "файл классов ввода-вывода [C++]"
  - "файлы [C++], обработка"
  - "файлы [C++], MFC - библиотека"
  - "файлы [C++], сериализация"
  - "ввод-вывод [C++], MFC - классы"
  - "Ввод и вывод [MFC]"
  - "MFC [C++], файловые операции"
  - "сохранение [C++]"
  - "сериализация [C++], MFC-файлы"
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Файлы в MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В библиотеки Microsoft Foundation Class \(MFC\), класс [CFile](../mfc/reference/cfile-class.md) обрабатывает операции ВВОДА\-ВЫВОДА обычного файла.  Это семейство статей описание способов открытия и закрытия файлов, так и для чтения и записи данных в эти файлы.  Также описывает операции состояния файла.  Описание использования, основанные на объектах функции MFC как альтернативный способ сериализации данных чтение и запись в файлах см. в статье [Сериализация](../Topic/Serialization%20in%20MFC.md).  
  
> [!NOTE]
>  При использовании объектов MFC **CDocument** платформа выполняет большую часть действий сериализации автоматически.  В частности, платформа создает и использует объект `CFile`.  Если необходимо написать код в переопределении функции\-члена `Serialize` класса **CDocument**.  
  
 Класс `CFile` предоставляет интерфейс для универсальных операций двоичного файла.  Классы `CStdioFile` и `CMemFile`, производные от `CFile` и `CSharedFile` производный класс из `CMemFile` предоставляют более специализированного сервисы файла.  
  
 Альтернативные дополнительных сведений в файл MFC, см. в разделе [Обработка файла](../c-runtime-library/file-handling.md) в *справочнике библиотеки времени выполнения*.  
  
 Дополнительные сведения о производных классах `CFile` см. в разделе [Диаграмма иерархии MFC](../mfc/hierarchy-chart.md).  
  
## Выберите действие.  
 *Используйте CFile*  
  
-   [Откройте файл с CFile](../Topic/Opening%20Files.md)  
  
-   [Чтение и запись файла с CFile](../mfc/reading-and-writing-files.md)  
  
-   [Закройте файл с CFile](../mfc/closing-files.md)  
  
-   [Чтобы получить состояние файла с CFile](../mfc/accessing-file-status.md)  
  
 *Используйте сериализации MFC \(сохранение объекта\)*  
  
-   [Создать сериализуемый класс](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Выполните сериализацию объекта через объект CArchive](../Topic/Serialization:%20Serializing%20an%20Object.md)  
  
-   [Создайте объект CArchive](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [Используйте CArchive \<\< и \>\> операторы](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [Сохраните и нагружайте CObjects и CObject\- производных объектов с помощью архив](../Topic/Storing%20and%20Loading%20CObjects%20via%20an%20Archive.md)  
  
## См. также  
 [Принцип I: Используйте класс CFile?](http://go.microsoft.com/fwlink/?LinkId=128046)   
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [CArchive Class](../mfc/reference/carchive-class.md)   
 [CObject Class](../Topic/CObject%20Class.md)