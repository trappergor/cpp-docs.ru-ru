---
title: "CTokenPrivileges Class | Microsoft Docs"
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
  - "ATL::CTokenPrivileges"
  - "CTokenPrivileges"
  - "ATL.CTokenPrivileges"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenPrivileges class"
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTokenPrivileges Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры **TOKEN\_PRIVILEGES**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CTokenPrivileges  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTokenPrivileges::CTokenPrivileges](../Topic/CTokenPrivileges::CTokenPrivileges.md)|Конструктор.|  
|[CTokenPrivileges::~CTokenPrivileges](../Topic/CTokenPrivileges::~CTokenPrivileges.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTokenPrivileges::Add](../Topic/CTokenPrivileges::Add.md)|Добавляет один или несколько прав доступа к объекту `CTokenPrivileges`.|  
|[CTokenPrivileges::Delete](../Topic/CTokenPrivileges::Delete.md)|Удаляет право доступа из объекта `CTokenPrivileges`.|  
|[CTokenPrivileges::DeleteAll](../Topic/CTokenPrivileges::DeleteAll.md)|Удаляет все права из объекта `CTokenPrivileges`.|  
|[CTokenPrivileges::GetCount](../Topic/CTokenPrivileges::GetCount.md)|Возвращает число записей в объекте `CTokenPrivileges` прав доступа.|  
|[CTokenPrivileges::GetDisplayNames](../Topic/CTokenPrivileges::GetDisplayNames.md)|Получить отображаемые имена для прав доступа, содержащихся в `CTokenPrivileges` объект.|  
|[CTokenPrivileges::GetLength](../Topic/CTokenPrivileges::GetLength.md)|Возвращает размер буфера в байтах, необходимое для хранения структуры **TOKEN\_PRIVILEGES**, представленного объектом `CTokenPrivileges`.|  
|[CTokenPrivileges::GetLuidsAndAttributes](../Topic/CTokenPrivileges::GetLuidsAndAttributes.md)|Извлекает локально уникальные идентификаторы \(LUID\) и флаги атрибута из объекта `CTokenPrivileges`.|  
|[CTokenPrivileges::GetNamesAndAttributes](../Topic/CTokenPrivileges::GetNamesAndAttributes.md)|Возвращает флаги имен и атрибутов привилегий от объекта `CTokenPrivileges`.|  
|[CTokenPrivileges::GetPTOKEN\_PRIVILEGES](../Topic/CTokenPrivileges::GetPTOKEN_PRIVILEGES.md)|Возвращает указатель на структуру **TOKEN\_PRIVILEGES**.|  
|[CTokenPrivileges::LookupPrivilege](../Topic/CTokenPrivileges::LookupPrivilege.md)|Извлекает атрибут, связанный с заданным именем прав доступа.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTokenPrivileges::operator const TOKEN\_PRIVILEGES \*](../Topic/CTokenPrivileges::operator%20const%20TOKEN_PRIVILEGES%20*.md)|Приводит значение к указателю на структуру **TOKEN\_PRIVILEGES**.|  
|[CTokenPrivileges::operator \=](../Topic/CTokenPrivileges::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 [маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) объект, описывающий контекст безопасности процесса или потока и выделен к каждому пользователю внесенному в журнал в систему Windows NT 2000 или Windows.  
  
 Маркер доступа используется для описания разные привилегии безопасности предоставлять для каждого пользователя.  Привилегия состоит из 64 разрядного числа вызванного локально уникальным идентификатором строки \([LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)\) и дескриптора.  
  
 Класс `CTokenPrivileges` программа\-оболочка для структуры [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) и содержит 0 или больше привилегий.  Права доступа можно добавлять, удалять или запросить с помощью предоставленных методы класса.  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Пример безопасности](../../top/visual-cpp-samples.md)   
 [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID\_AND\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)