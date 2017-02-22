---
title: "CTokenGroups Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenGroups"
  - "ATL.CTokenGroups"
  - "CTokenGroups"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenGroups class"
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CTokenGroups Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры **TOKEN\_GROUPS**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CTokenGroups  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTokenGroups::CTokenGroups](../Topic/CTokenGroups::CTokenGroups.md)|Конструктор.|  
|[CTokenGroups::~CTokenGroups](../Topic/CTokenGroups::~CTokenGroups.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTokenGroups::Add](../Topic/CTokenGroups::Add.md)|Добавляет `CSid` или существующие структуры **TOKEN\_GROUPS** к объекту `CTokenGroups`.|  
|[CTokenGroups::Delete](../Topic/CTokenGroups::Delete.md)|Удаляет `CSid` и связанные с ним атрибуты из объекта `CTokenGroups`.|  
|[CTokenGroups::DeleteAll](../Topic/CTokenGroups::DeleteAll.md)|Удаляет все объекты `CSid` и связанные с ними атрибуты из объекта `CTokenGroups`.|  
|[CTokenGroups::GetCount](../Topic/CTokenGroups::GetCount.md)|Возвращает количество объектов `CSid` и связанных с ними атрибутов, содержащихся в объекте **CTokenGroups** .|  
|[CTokenGroups::GetLength](../Topic/CTokenGroups::GetLength.md)|Возвращает размер объекта `CTokenGroups`.|  
|[CTokenGroups::GetPTOKEN\_GROUPS](../Topic/CTokenGroups::GetPTOKEN_GROUPS.md)|Извлекает указатель на структуру **TOKEN\_GROUPS**.|  
|[CTokenGroups::GetSidsAndAttributes](../Topic/CTokenGroups::GetSidsAndAttributes.md)|Извлекает объекты и атрибуты `CSid`, принадлежащих объекту `CTokenGroups`.|  
|[CTokenGroups::LookupSid](../Topic/CTokenGroups::LookupSid.md)|Получает атрибуты, связанные с объектом `CSid`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTokenGroups::operator const TOKEN\_GROUPS \*](../Topic/CTokenGroups::operator%20const%20TOKEN_GROUPS%20*.md)|Приводит объект `CTokenGroups` на указатель на структуру **TOKEN\_GROUPS**.|  
|[CTokenGroups::operator \=](../Topic/CTokenGroups::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 [маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) объект, описывающий контекст безопасности процесса или потока и выделен к каждому пользователю внесенному в журнал в систему Windows NT 2000 или Windows.  
  
 Класс **CTokenGroups** программа\-оболочка для структуры [TOKEN\_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624), содержащий сведения об идентификаторах безопасности группы \(sid\) в маркере доступа.  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Пример безопасности](../../top/visual-cpp-samples.md)   
 [CSid Class](../../atl/reference/csid-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)