---
title: "CGopherFileFind Class | Microsoft Docs"
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
  - "CGopherFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFileFind class"
  - "поиск файлов [C++]"
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Помощь в поиске файлов Интернета серверов gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены нерекомендуемый, поскольку они не работают на платформе Windows XP, но они продолжат работать на предыдущих платформах.  
  
## Синтаксис  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGopherFileFind::CGopherFileFind](../Topic/CGopherFileFind::CGopherFileFind.md)|Создает объект `CGopherFileFind`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md)|Файл на сервер gopher.|  
|[CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md)|Продолжает поиск файла в результате предыдущего вызова метода [FindFile](../Topic/CGopherFileFind::FindFile.md).|  
|[CGopherFileFind::GetCreationTime](../Topic/CGopherFileFind::GetCreationTime.md)|Получает время указанный файл был создан.|  
|[CGopherFileFind::GetLastAccessTime](../Topic/CGopherFileFind::GetLastAccessTime.md)|Возвращает указанный время последнего доступа.|  
|[CGopherFileFind::GetLastWriteTime](../Topic/CGopherFileFind::GetLastWriteTime.md)|Получает время указанный файл последней записи.|  
|[CGopherFileFind::GetLength](../Topic/CGopherFileFind::GetLength.md)|Получает длину найденного файла в байтах.|  
|[CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md)|Получите объект `CGopherLocator`.|  
|[CGopherFileFind::GetScreenName](../Topic/CGopherFileFind::GetScreenName.md)|Возвращает имя экрана gopher.|  
|[CGopherFileFind::IsDots](../Topic/CGopherFileFind::IsDots.md)|Тесты для меток текущей папки и родительского каталога, пока повторенный между файлами.|  
  
## Заметки  
 `CGopherFileFind` содержит функции\-члены, начинающиеся поиск, обнаруживают файл, и возвращает URL\-адрес файла.  
  
 Другие классы MFC, разработанные для поиска в интернете и локального файла, которые содержат [CFtpFileFind](../Topic/CFtpFileFind%20Class.md) и [CFileFind](../../mfc/reference/cfilefind-class.md).  Вместе с `CGopherFileFind` эти классы обеспечивают бесшовный механизм для пользователя для поиска конкретных файлов, независимо от протокола сервера, типа файла или расположение \(или локальный компьютер или удаленный сервер\). Обратите внимание, что класс MFC для поиска для HTTP\-сервера, поскольку HTTP не поддерживает обработку непосредственно файла необходимо поисками.  
  
> [!NOTE]
>  `CGopherFileFind` не поддерживает следующие функции\-члены его базового класса [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
-   [GetRoot](../Topic/CFileFind::GetRoot.md)  
  
-   [GetFileName](../Topic/CFileFind::GetFileName.md)  
  
-   [GetFilePath](../Topic/CFileFind::GetFilePath.md)  
  
-   [GetFileTitle](../Topic/CFileFind::GetFileTitle.md)  
  
-   [GetFileURL](../Topic/CFileFind::GetFileURL.md)  
  
 Кроме того, при использовании с `CGopherFileFind`, функция\-член [IsDots](../Topic/CFileFind::IsDots.md)`CFileFind` всегда **FALSE**.  
  
 Дополнительные сведения об использовании `CGopherFileFind` и другие классы WinInet см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../Topic/CFtpFileFind%20Class.md)   
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../Topic/CHttpFile%20Class.md)