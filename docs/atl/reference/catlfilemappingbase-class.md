---
title: "CAtlFileMappingBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlFileMappingBase"
  - "ATL::CAtlFileMappingBase"
  - "CAtlFileMappingBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMappingBase class"
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlFileMappingBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет размещенный в памяти файл.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CAtlFileMappingBase  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](../Topic/CAtlFileMappingBase::CAtlFileMappingBase.md)|Конструктор.|  
|[CAtlFileMappingBase::~CAtlFileMappingBase](../Topic/CAtlFileMappingBase::~CAtlFileMappingBase.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlFileMappingBase::CopyFrom](../Topic/CAtlFileMappingBase::CopyFrom.md)|Вызовите этот метод, чтобы скопировать из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::GetData](../Topic/CAtlFileMappingBase::GetData.md)|Вызовите этот метод, чтобы получить данные из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::GetHandle](../Topic/CAtlFileMappingBase::GetHandle.md)|Вызывайте этот метод для возврата дескриптора файла.|  
|[CAtlFileMappingBase::GetMappingSize](../Topic/CAtlFileMappingBase::GetMappingSize.md)|Вызовите этот метод, чтобы получить размер объекта сопоставления от сопоставления файлов.|  
|[CAtlFileMappingBase::MapFile](../Topic/CAtlFileMappingBase::MapFile.md)|Вызовите этот метод, чтобы создать объект сопоставления файлов.|  
|[CAtlFileMappingBase::MapSharedMem](../Topic/CAtlFileMappingBase::MapSharedMem.md)|Вызовите этот метод, чтобы создать объект сопоставления файлов, который обеспечивает полный доступ ко всем процессам.|  
|[CAtlFileMappingBase::OpenMapping](../Topic/CAtlFileMappingBase::OpenMapping.md)|Вызывайте этот метод для возврата дескриптора на объект сопоставления файлов.|  
|[CAtlFileMappingBase::Unmap](../Topic/CAtlFileMappingBase::Unmap.md)|Этот метод вызывается в unmap объект сопоставления файлов.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlFileMappingBase::operator \=](../Topic/CAtlFileMappingBase::operator%20=.md)|Устанавливает текущий объект сопоставления файлов на другой объект сопоставления файлов.|  
  
## Заметки  
 Сопоставление ассоциаций файлов содержимого файла с частью виртуального адресного пространства процесса.  Этот класс содержит методы для создания объектов сопоставления файлов, которые позволяют легко программы доступа и используют данные.  
  
 Дополнительные сведения см. в разделе [сопоставление файлов](http://msdn.microsoft.com/library/windows/desktop/aa366556) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlfile.h  
  
## См. также  
 [CAtlFileMapping Class](../Topic/CAtlFileMapping%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)