---
title: "CAtlTemporaryFile Class | Microsoft Docs"
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
  - "CAtlTemporaryFile"
  - "ATL.CAtlTemporaryFile"
  - "ATL::CAtlTemporaryFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTemporaryFile class"
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlTemporaryFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для создания и использования временного файла.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CAtlTemporaryFile  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md)|Конструктор.|  
|[CAtlTemporaryFile::~CAtlTemporaryFile](../Topic/CAtlTemporaryFile::~CAtlTemporaryFile.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlTemporaryFile::Close](../Topic/CAtlTemporaryFile::Close.md)|Вызовите этот метод, чтобы закрыть временный файл и или для удаления содержимого или сохранить их с указанным именем файла.|  
|[CAtlTemporaryFile::Create](../Topic/CAtlTemporaryFile::Create.md)|Вызовите этот метод, чтобы создать временный файл.|  
|[CAtlTemporaryFile::Flush](../Topic/CAtlTemporaryFile::Flush.md)|Вызовите этот метод, чтобы заставить все данные, остающихся в файловом буфер для записи к временному файлу.|  
|[CAtlTemporaryFile::GetPosition](../Topic/CAtlTemporaryFile::GetPosition.md)|Вызовите этот метод, чтобы получить положение указателя текущего файла.|  
|[CAtlTemporaryFile::GetSize](../Topic/CAtlTemporaryFile::GetSize.md)|Вызовите этот метод, чтобы получить размер в байтах для временных файлов.|  
|[CAtlTemporaryFile::HandsOff](../Topic/CAtlTemporaryFile::HandsOff.md)|Вызовите этот метод, чтобы отделить файл из объекта `CAtlTemporaryFile`.|  
|[CAtlTemporaryFile::HandsOn](../Topic/CAtlTemporaryFile::HandsOn.md)|Вызовите этот метод, чтобы открыть существующий временный файл и разместить указатель в конце файла.|  
|[CAtlTemporaryFile::LockRange](../Topic/CAtlTemporaryFile::LockRange.md)|Этот метод вызывается для блокирования область в файле, чтобы предотвратить доступ к ней других процессов.|  
|[CAtlTemporaryFile::Read](../Topic/CAtlTemporaryFile::Read.md)|Этот метод вызывается для считывания данных из временного файла, начиная с позиции, указываемой указателем файла.|  
|[CAtlTemporaryFile::Seek](../Topic/CAtlTemporaryFile::Seek.md)|Вызовите этот метод, чтобы переместить указатель файла для временных файлов.|  
|[CAtlTemporaryFile::SetSize](../Topic/CAtlTemporaryFile::SetSize.md)|Вызовите этот метод, чтобы задать размер временного файла.|  
|[CAtlTemporaryFile::TempFileName](../Topic/CAtlTemporaryFile::TempFileName.md)|Вызовите этот метод, чтобы получить имя временного файла.|  
|[CAtlTemporaryFile::UnlockRange](../Topic/CAtlTemporaryFile::UnlockRange.md)|Вызовите этот метод, чтобы Разблокировать область временного файла.|  
|[CAtlTemporaryFile::Write](../Topic/CAtlTemporaryFile::Write.md)|Вызывайте этот метод для записи данных к временному файлу, начиная с позиции, указываемой указателем файла.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlTemporaryFile::operator HANDLE](../Topic/CAtlTemporaryFile::operator%20HANDLE.md)|Возвращает дескриптор к временному файлу.|  
  
## Заметки  
 `CAtlTemporaryFile` упрощает создание и использование временный файл.  Файл автоматически открывается, называется, закрыть и удаления.  Если содержимое файла не требуются, то после того, как файл закрыть, их можно сохранить в новый файл с указанным именем.  
  
## Требования  
 **Header:** atlfile.h  
  
## Пример  
 См. пример для [CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md).  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CAtlFile Class](../../atl/reference/catlfile-class.md)