---
title: "CFileFind Class | Microsoft Docs"
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
  - "CFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileFind class"
  - "файлы [C++], поиск"
  - "Internet files [C++], поиск"
  - "local files"
  - "local files, поиск"
  - "URLs [C++], поиск"
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет поиск файла локальные и базовый класс для [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) и [CFtpFileFind](../Topic/CFtpFileFind%20Class.md), которые выполняют поиск файлов Интернета.  
  
## Синтаксис  
  
```  
class CFileFind : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileFind::CFileFind](../Topic/CFileFind::CFileFind.md)|Создает объект `CFileFind`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileFind::Close](../Topic/CFileFind::Close.md)|Закрывает запрос поиска.|  
|[CFileFind::FindFile](../Topic/CFileFind::FindFile.md)|Ищет каталог для указанного имени файла.|  
|[CFileFind::FindNextFile](../Topic/CFileFind::FindNextFile.md)|Продолжает поиск файла в результате предыдущего вызова метода [FindFile](../Topic/CFileFind::FindFile.md).|  
|[CFileFind::GetCreationTime](../Topic/CFileFind::GetCreationTime.md)|Получает время файл был создан.|  
|[CFileFind::GetFileName](../Topic/CFileFind::GetFileName.md)|Возвращает имя \(включая расширение файла, найденного|  
|[CFileFind::GetFilePath](../Topic/CFileFind::GetFilePath.md)|Возвращает полный путь не найден.|  
|[CFileFind::GetFileTitle](../Topic/CFileFind::GetFileTitle.md)|Получает название найденного файла.  Заголовок не включает расширение.|  
|[CFileFind::GetFileURL](../Topic/CFileFind::GetFileURL.md)|Возвращает URL\-адрес, включая путь к файлу, найденного файла.|  
|[CFileFind::GetLastAccessTime](../Topic/CFileFind::GetLastAccessTime.md)|Получает время последнего доступа.|  
|[CFileFind::GetLastWriteTime](../Topic/CFileFind::GetLastWriteTime.md)|Возвращает время последнего изменения и сохранить.|  
|[CFileFind::GetLength](../Topic/CFileFind::GetLength.md)|Получает длину найденного файла в байтах.|  
|[CFileFind::GetRoot](../Topic/CFileFind::GetRoot.md)|Возвращает корневой каталог файлов не найден.|  
|[CFileFind::IsArchived](../Topic/CFileFind::IsArchived.md)|Определяет, если обнаружен файл сжат.|  
|[CFileFind::IsCompressed](../Topic/CFileFind::IsCompressed.md)|Определяет, если обнаружен файл сжат.|  
|[CFileFind::IsDirectory](../Topic/CFileFind::IsDirectory.md)|Определяет, если обнаружен файл каталог.|  
|[CFileFind::IsDots](../Topic/CFileFind::IsDots.md)|Определяет, если имя найденного файла имеет имя "." или ". " указывающее, виртуальный каталог.|  
|[CFileFind::IsHidden](../Topic/CFileFind::IsHidden.md)|Определяет, если обнаружен файл скрыть.|  
|[CFileFind::IsNormal](../Topic/CFileFind::IsNormal.md)|Определяет, если обнаружен файл обычный \(иначе говоря, не имеющей других атрибутов\).|  
|[CFileFind::IsReadOnly](../Topic/CFileFind::IsReadOnly.md)|Определяет, если обнаружен файл только для чтения.|  
|[CFileFind::IsSystem](../Topic/CFileFind::IsSystem.md)|Определяет, если обнаружен файл является системным.|  
|[CFileFind::IsTemporary](../Topic/CFileFind::IsTemporary.md)|Определяет, если обнаружен файл является временным.|  
|[CFileFind::MatchesMask](../Topic/CFileFind::MatchesMask.md)|Указывает атрибуты нужного файла, который требуется найти.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileFind::CloseContext](../Topic/CFileFind::CloseContext.md)|Закрывает текущий файл, указанный дескриптором поиска.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileFind::m\_pTM](../Topic/CFileFind::m_pTM.md)|Указатель на объект `CAtlTransactionManager`.|  
  
## Заметки  
 `CFileFind` содержит функции\-члены, начинающиеся поиск, обнаруживают файл и возвращают имя, имя или путь к файлу.  Для поиска в интернете, функция\-член [GetFileURL](../Topic/CFileFind::GetFileURL.md) возвращает URL\-адрес файла.  
  
 2`CFileFind` базовый класс для других классов MFC, предназначенных для поиска типы указанного сервера. `CGopherFileFind` работает исключительно с серверами gopher и рабочими `CFtpFileFind` именно с ftp\-сервера.  Вместе эти 3 бесшовный класса предоставляют механизм для клиента, чтобы найти файлы, независимо от протокола сервера, типа файла или расположение на локальном компьютере или удаленном сервере.  
  
 В следующем коде приведен список всех файлов в текущей папке печать имя каждого файла:  
  
 [!code-cpp[NVC_MFCFiles#31](../../mfc/codesnippet/CPP/cfilefind-class_1.cpp)]  
  
 Для хранения примере простым, этот код использует стандартный класс `cout` библиотеки C\+\+.  Линия `cout` может быть заменена с вызовом `CListBox::AddString`, например, в программе с графическим пользовательским интерфейсом.  
  
 Дополнительные сведения об использовании `CFileFind` и другие классы WinInet см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CFileFind`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../Topic/CFtpFileFind%20Class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../Topic/CHttpFile%20Class.md)