---
title: "CMemFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemFile class"
  - "memory files"
  - "temporary files, memory files"
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMemFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CFile](../../mfc/reference/cfile-class.md)\- производный класс, который поддерживает файлы памяти.  
  
## Синтаксис  
  
```  
class CMemFile : public CFile  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMemFile::CMemFile](../Topic/CMemFile::CMemFile.md)|Создает объект файла памяти.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMemFile::Attach](../Topic/CMemFile::Attach.md)|Вложение блок памяти в `CMemFile`.|  
|[CMemFile::Detach](../Topic/CMemFile::Detach.md)|Наконец удаляет блок памяти из `CMemFile` и возвращает указатель на блок finally удаленному памяти.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMemFile::Alloc](../Topic/CMemFile::Alloc.md)|Переопределение, чтобы изменить поведение выделения памяти.|  
|[CMemFile::Free](../Topic/CMemFile::Free.md)|Переопределение, чтобы изменить поведение освобождение памяти.|  
|[CMemFile::GrowFile](../Topic/CMemFile::GrowFile.md)|Переопределение, чтобы изменить поведение увеличение файла.|  
|[CMemFile::Memcpy](../Topic/CMemFile::Memcpy.md)|Переопределение, чтобы изменить поведение копирования памяти при чтении и записи файлов.|  
|[CMemFile::Realloc](../Topic/CMemFile::Realloc.md)|Переопределение, чтобы изменить поведение перераспределения памяти.|  
  
## Заметки  
 Эти файлы памяти ведут себя как файлы на диске, за исключением того, что файл сохраняется в оперативной памяти, а не на диске.  Файл памяти полезен для временного хранения или для передачи необработанных байт или сериализованные объекты между независимыми процессами.  
  
 Объекты `CMemFile` могут автоматически выбрать собственную память, либо можно вложить собственный блок памяти в объект `CMemFile` путем вызова [Вложение](../Topic/CMemFile::Attach.md).  В любом случае, память для увеличение памяти файл автоматически выделена в `nGrowBytes`\- указанных размеров шагом при `nGrowBytes` не равно нулю.  
  
 Блок памяти будет автоматически удален при разрушении объекта `CMemFile` если память была изначально выделена объектом `CMemFile`; в противном случае ответственность за deallocating память для вложили к объекту.  
  
 Можно получить доступ к блок памяти через предоставленный указатель, когда наконец удалить ее из объекта `CMemFile` путем вызова [Наконец удалить](../Topic/CMemFile::Detach.md).  
  
 Чаще всего используется `CMemFile` создать объект `CMemFile` и использовать ее с помощью вызова функции\-члены [CFile](../../mfc/reference/cfile-class.md).  Обратите внимание, что создание `CMemFile` автоматически открывает его. [CFile::Open](../Topic/CFile::Open.md), которые не вызываются только используется для файлов на диске.  Поскольку `CMemFile` не использует файл на диске, не используется и не имеет член данных `CFile::m_hFile` смысла.  
  
 Функции\-члены [дубликат](../Topic/CFile::Duplicate.md), [LockRange](../Topic/CFile::LockRange.md) и [UnlockRange](../Topic/CFile::UnlockRange.md)`CFile` не реализованы для `CMemFile`.  Если вызвать эти функции в `CMemFile` объект, обращающихся [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` использует функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md) и [free](../../c-runtime-library/reference/free.md) для выбора, reallocate и отмены выделения памяти; и внутренние [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) чтобы отключить память копии при чтении и записи.  Если требуется изменить эту функциональности или функциональности, то при `CMemFile` файл растет, создайте собственный класс, производный от `CMemFile` и переопределить соответствующие функции.  
  
 Дополнительные сведения о `CMemFile` см. в разделе статьи [файлы в MFC](../../mfc/files-in-mfc.md) и [управление памятью \(MFC\)](../../mfc/memory-management.md) и [Обработка файла](../../c-runtime-library/file-handling.md) см. в документации по *библиотеке времени выполнения*.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)