---
title: "CAcl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAcl"
  - "ATL::CAcl"
  - "ATLSECURITY/CAcl"
  - "ATL.CAcl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAcl class"
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAcl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры `ACL` \(acl\).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CAcl  
  
```  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CAcl::CAccessMaskArray](../Topic/CAcl::CAccessMaskArray.md)|Массив `ACCESS_MASK`.|  
|[CAcl::CAceFlagArray](../Topic/CAcl::CAceFlagArray.md)|Массив `BYTE`.|  
|[CAcl::CAceTypeArray](../Topic/CAcl::CAceTypeArray.md)|Массив `BYTE`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAcl::CAcl](../Topic/CAcl::CAcl.md)|Конструктор.|  
|[CAcl::~CAcl](../Topic/CAcl::~CAcl.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAcl::GetAceCount](../Topic/CAcl::GetAceCount.md)|Возвращает количество объектов элементов управления доступом \(ACE\).|  
|[CAcl::GetAclEntries](../Topic/CAcl::GetAclEntries.md)|Извлекает записи acl \(ACL\) из объекта `CAcl`.|  
|[CAcl::GetAclEntry](../Topic/CAcl::GetAclEntry.md)|Извлекает все сведения о записи в объекте `CAcl`.|  
|[CAcl::GetLength](../Topic/CAcl::GetLength.md)|Возвращает длину ACL.|  
|[CAcl::GetPACL](../Topic/CAcl::GetPACL.md)|Возвращает указатель на PACL \(ACL\).|  
|[CAcl::IsEmpty](../Topic/CAcl::IsEmpty.md)|Проверяет объект `CAcl` для записей.|  
|[CAcl::IsNull](../Topic/CAcl::IsNull.md)|Возвращает состояние объекта `CAcl`.|  
|[CAcl::RemoveAce](../Topic/CAcl::RemoveAce.md)|Удаляет указанный элемент управления доступом \(ACE\) из объекта `CAcl`.|  
|[CAcl::RemoveAces](../Topic/CAcl::RemoveAces.md)|Удаляет все элементы управления доступом \(элементы управления доступом\) из `CAcl`, которые применяются к данным `CSid`.|  
|[CAcl::SetEmpty](../Topic/CAcl::SetEmpty.md)|Отмечает объект `CAcl` как пустой.|  
|[CAcl::SetNull](../Topic/CAcl::SetNull.md)|Отмечает объект `CAcl` как `NULL`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAcl::operator const ACL \*](../Topic/CAcl::operator%20const%20ACL%20*.md)|Объект `CAcl` приводит к структуре `ACL`.|  
|[CAcl::operator \=](../Topic/CAcl::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 Структура **ACL** заголовок ACL \(acl\).  Последовательный список ACL позволяет [Элементы управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374868) \(ноль или более элементов управления доступом\).  В отдельные элементы управления доступом ACL нумеруются от 0 до *n\-1*, где *n* \- количество тузов в ACL.  При редактировании ACL, приложение ссылается на элемент управления доступом \(ACE\) в рамках списков ACL по индексу.  
  
 2 Типа списков ACL:  
  
-   Дискреционный  
  
-   Система  
  
 Дискреционное ACL управляется владельцем объекта или любой пользователь **WRITE\_DAC** доступ к объекту.  Он определяет пользователи и группы могут доступа указанный объект.  Например, владелец файла может использоваться дискреционное ACL для наблюдения за которым пользователи и группы могут и не могут иметь доступ к файлу.  
  
 Объект также может содержать сведения о безопасности система\- уровня связанная с ним, в форме ACL системы управляемого администратором.  Системный администратор может включить ACL для аудита все попытки получить доступ к объекту.  
  
 Дополнительные сведения см. в разделе обсуждение [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)