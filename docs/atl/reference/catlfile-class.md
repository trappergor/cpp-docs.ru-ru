---
title: "CAtlFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlFile"
  - "ATL::CAtlFile"
  - "ATL.CAtlFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFile class"
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAtlFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит программу\-оболочку вокруг обработки файл\- тонкая Windows API.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CAtlFile : public CHandle  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlFile::CAtlFile](../Topic/CAtlFile::CAtlFile.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlFile::Create](../Topic/CAtlFile::Create.md)|Вызывайте этот метод для создания или открытия файла.|  
|[CAtlFile::Flush](../Topic/CAtlFile::Flush.md)|Вызовите этот метод, чтобы очистить буферы для файла и вызвать всех буферизованных данных в файл.|  
|[CAtlFile::GetOverlappedResult](../Topic/CAtlFile::GetOverlappedResult.md)|Этот метод вызывается для получения результатов перекрытой операции в файле.|  
|[CAtlFile::GetPosition](../Topic/CAtlFile::GetPosition.md)|Вызовите этот метод, чтобы получить положение указателя текущего файла из файла.|  
|[CAtlFile::GetSize](../Topic/CAtlFile::GetSize.md)|Вызовите этот метод, чтобы получить размер файла в байтах.|  
|[CAtlFile::LockRange](../Topic/CAtlFile::LockRange.md)|Этот метод вызывается для блокирования область в файле, чтобы предотвратить доступ к ней других процессов.|  
|[CAtlFile::Read](../Topic/CAtlFile::Read.md)|Этот метод вызывается для считывания данных из файла, начиная с позиции, указываемой указателем файла.|  
|[CAtlFile::Seek](../Topic/CAtlFile::Seek.md)|Вызовите этот метод, чтобы переместить указатель файла.|  
|[CAtlFile::SetSize](../Topic/CAtlFile::SetSize.md)|Вызовите этот метод, чтобы задать размер файла.|  
|[CAtlFile::UnlockRange](../Topic/CAtlFile::UnlockRange.md)|Вызовите этот метод, чтобы Разблокировать области файла.|  
|[CAtlFile::Write](../Topic/CAtlFile::Write.md)|Вызывайте этот метод для записи данных в файл, начиная с позиции, указываемой указателем файла.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlFile::m\_pTM](../Topic/CAtlFile::m_pTM.md)|Указатель на объект `CAtlTransactionManager`|  
  
## Заметки  
 Используйте этот класс файл\- при обработке необходимости относительно простым, но больше абстракции, чем API Windows предоставляет необходимости без включения зависимости MFC.  
  
## Иерархия наследования  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## Требования  
 **Header:** atlfile.h  
  
## См. также  
 [Образец бегущей строки](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CHandle Class](../../atl/reference/chandle-class.md)