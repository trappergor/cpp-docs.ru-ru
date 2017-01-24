---
title: "CFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class, using with CFile"
  - "CFile class"
  - "файлы [C++], classes for"
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для файлов Microsoft foundation class сортировать по.  
  
## Синтаксис  
  
```  
class CFile : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFile::CFile](../Topic/CFile::CFile.md)|Создает объект `CFile` из дескриптора пути или файла.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFile::Abort](../Topic/CFile::Abort.md)|Закрывает файл игнорируя все предупреждения и ошибки.|  
|[CFile::Close](../Topic/CFile::Close.md)|Закрывает и удаляет объект.|  
|[CFile::Duplicate](../Topic/CFile::Duplicate.md)|Создает дубликат объекта, основанного на этом файле.|  
|[CFile::Flush](../Topic/CFile::Flush.md)|Сбрасывает все данные, которые требуется записать.|  
|[CFile::GetFileName](../Topic/CFile::GetFileName.md)|Извлекает имя файла, выбранного файла.|  
|[CFile::GetFilePath](../Topic/CFile::GetFilePath.md)|Получает полный путь к файлу, выбранному файлу.|  
|[CFile::GetFileTitle](../Topic/CFile::GetFileTitle.md)|Возвращает имя выбранного файла.|  
|[CFile::GetLength](../Topic/CFile::GetLength.md)|Получает длину файла.|  
|[CFile::GetPosition](../Topic/CFile::GetPosition.md)|Извлекает указатель текущего файла.|  
|[CFile::GetStatus](../Topic/CFile::GetStatus.md)|Извлекает состояние открытия файла или в статической версии, извлекает состояние указанного файла \(статического виртуальная функция\).|  
|[CFile::LockRange](../Topic/CFile::LockRange.md)|Блокирует диапазон байтов в файле.|  
|[CFile::Open](../Topic/CFile::Open.md)|Safe открывает файл с параметром ошибка\- тестирования.|  
|[CFile::Read](../Topic/CFile::Read.md)|Считывает \(небуферизованный\) данные из файла в позиции текущего файла.|  
|[CFile::Remove](../Topic/CFile::Remove.md)|Удаляет указанный файл \(статическая функция.|  
|[CFile::Rename](../Topic/CFile::Rename.md)|Переименовывает указанный файл \(статическая функция.|  
|[CFile::Seek](../Topic/CFile::Seek.md)|Располагает указатель текущего файла.|  
|[CFile::SeekToBegin](../Topic/CFile::SeekToBegin.md)|Располагает указатель текущего файла в начале файла.|  
|[CFile::SeekToEnd](../Topic/CFile::SeekToEnd.md)|Располагает указатель текущего файла в конце файла.|  
|[CFile::SetFilePath](../Topic/CFile::SetFilePath.md)|Задает полный путь к файлу, выбранному файлу.|  
|[CFile::SetLength](../Topic/CFile::SetLength.md)|Изменяет размер файла.|  
|[CFile::SetStatus](../Topic/CFile::SetStatus.md)|Устанавливает состояние указанного файла \(статического виртуальная функция\).|  
|[CFile::UnlockRange](../Topic/CFile::UnlockRange.md)|Разблокирует диапазон байтов в файле.|  
|[CFile::Write](../Topic/CFile::Write.md)|Записывает данные \(небуферизованный\) в файле позиции текущего файла.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFile::operator HANDLE](../Topic/CFile::operator%20HANDLE.md)|Дескриптор объекта `CFile`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFile::hFileNull](../Topic/CFile::hFileNull.md)|Определяет, если объект `CFile` имеет допустимого дескриптора.|  
|[CFile::m\_hFile](../Topic/CFile::m_hFile.md)|Обычно содержит дескриптор файла операционной системы.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFile::m\_pTM](../Topic/CFile::m_pTM.md)|Указатель на объект `CAtlTransactionManager`.|  
  
## Заметки  
 Он прямо предоставляет небуферизованный, двоичные службы ввода\-вывода диска, и он косвенно поддерживает текстовые файлы и файлы памяти через его производные классы.  Рабочие `CFile` совместно с классом `CArchive` для поддержки сериализации класса Microsoft foundation объект.  
  
 Иерархические связи между этим классом и его производных классов позволяет программе, чтобы работать с переданным ей все объекты файла с помощью полиморфный интерфейс `CFile`.  Файл памяти, например ведет себя как файл на диске.  
  
 Используйте `CFile` и его производные классы для общецелевого дискового ввода\-вывода.  Используйте `ofstream` или другие классы iostream Майкрософт для форматированного текста, отправленного в файл на диске.  
  
 Обычно на диске файл открывается автоматически при создании `CFile` и закрыть на разрушении.  Статические функции\-члены позволяют также запрашивать состояние файлов, не открывая файл.  
  
 Дополнительные сведения об использовании `CFile` см. в разделе статьи [файлы в MFC](../../mfc/files-in-mfc.md) и [Обработка файла](../../c-runtime-library/file-handling.md) в справочнике по *библиотеке времени выполнения*.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CFile`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [Пытается MFC DRAWCLI](../../top/visual-cpp-samples.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CStdioFile Class](../Topic/CStdioFile%20Class.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [Инструкции: используйте класс CFile?](http://go.microsoft.com/fwlink/?LinkId=128046)