---
title: "CInternetFile Class | Microsoft Docs"
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
  - "CInternetFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetFile class"
  - "Internet files"
  - "Internet files, CInternetFile class"
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Разрешает доступ к файлам в удаленных системах, использующих протоколы Интернета.  
  
## Синтаксис  
  
```  
  
class CInternetFile : public CStdioFile  
  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInternetFile::CInternetFile](../Topic/CInternetFile::CInternetFile.md)|Создает объект `CInternetFile`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInternetFile::Abort](../Topic/CInternetFile::Abort.md)|Закрывает файл на все предупреждения и ошибки.|  
|[CInternetFile::Close](../Topic/CInternetFile::Close.md)|`CInternetFile` закрывает и освобождает свои ресурсы.|  
|[CInternetFile::Flush](../Topic/CInternetFile::Flush.md)|Сбрасывает содержимое буфера записи и гарантирует, что данные в памяти записаны к механической мишени.|  
|[CInternetFile::GetLength](../Topic/CInternetFile::GetLength.md)|Возвращает размер файла.|  
|[CInternetFile::Read](../Topic/CInternetFile::Read.md)|Считывает указанное число байтов.|  
|[CInternetFile::ReadString](../Topic/CInternetFile::ReadString.md)|Считывает поток символов.|  
|[CInternetFile::Seek](../Topic/CInternetFile::Seek.md)|Перемещает указатель в открытом файле.|  
|[CInternetFile::SetReadBufferSize](../Topic/CInternetFile::SetReadBufferSize.md)|Устанавливает размер буфера, в котором данные будут прочитаны.|  
|[CInternetFile::SetWriteBufferSize](../Topic/CInternetFile::SetWriteBufferSize.md)|Устанавливает размер буфера, в котором данные будут записаны.|  
|[CInternetFile::Write](../Topic/CInternetFile::Write.md)|Записывает указанное число байтов.|  
|[CInternetFile::WriteString](../Topic/CInternetFile::WriteString.md)|Записывает null\- готовая строка в файл.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInternetFile::operator HINTERNET](../Topic/CInternetFile::operator%20HINTERNET.md)|Оператор приведения для маркера Интернета.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CInternetFile::m\_hFile](../Topic/CInternetFile::m_hFile.md)|Дескриптор к файлу.|  
  
## Заметки  
 Предоставляет базовый класс для [CHttpFile](../Topic/CHttpFile%20Class.md) и файл [CGopherFile](../../mfc/reference/cgopherfile-class.md) классифицирует.  Никогда не создает объект `CInternetFile` напрямую.  Вместо этого создайте объект одного из его производных классов путем вызова [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md) или [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).  Также можно создать объект `CInternetFile` путем вызова [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md).  
  
 Функции\-члены **Открыть**, `LockRange`, `UnlockRange` и `Duplicate``CInternetFile` не реализованы для `CInternetFile`.  Если вызвать эти функции в `CInternetFile` объект, обращающихся [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CInternetFile` работает с другими классами MFC Интернета см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../Topic/CStdioFile%20Class.md)  
  
 `CInternetFile`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CStdioFile Class](../Topic/CStdioFile%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)