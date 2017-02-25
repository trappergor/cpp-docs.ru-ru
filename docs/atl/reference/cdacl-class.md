---
title: "CDacl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDacl"
  - "CDacl"
  - "ATL.CDacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDacl class"
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CDacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры DACL \(список управления доступом на уровне пользователей\).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CDacl : public CAcl  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDacl::CDacl](../Topic/CDacl::CDacl.md)|Конструктор.|  
|[CDacl::~CDacl](../Topic/CDacl::~CDacl.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDacl::AddAllowedAce](../Topic/CDacl::AddAllowedAce.md)|Добавляет разрешенный элемент управления доступом \(ACE\) на объект `CDacl`.|  
|[CDacl::AddDeniedAce](../Topic/CDacl::AddDeniedAce.md)|Добавляет этому управления доступом к объекту `CDacl`.|  
|[CDacl::GetAceCount](../Topic/CDacl::GetAceCount.md)|Возвращает количество тузов \(элементов управления доступом\) в объекте `CDacl`.|  
|[CDacl::RemoveAce](../Topic/CDacl::RemoveAce.md)|Удаляет указанный элемент управления доступом \(ACE\) из объекта `CDacl`.|  
|[CDacl::RemoveAllAces](../Topic/CDacl::RemoveAllAces.md)|Удаляет все элементы управления доступом, содержащихся в объекте `CDacl`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDacl::operator \=](../Topic/CDacl::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 Дескриптор безопасности объекта может содержать список DACL.  DACL содержащий ноль или более тузов \(элементы управления доступом\), указывающих пользователей и групп, имеющих доступ к объекту.  Если список управления доступом на уровне пользователей пустым \(т е он содержит нулевые элементы управления доступом\), то явным образом не предоставлять доступ, поэтому явно запретить доступ.  Однако если дескриптор безопасности объекта не имеет DACL, то объект незащищен и каждая из них имеет полный доступ.  
  
 Получение списка DACL объекта, необходимо быть владельцем объекта или READ\_CONTROL иметь доступ к объекту.  Изменение списка DACL объекта, необходимо иметь доступ WRITE\_DAC к объекту.  
  
 Использование методов класса, предоставляемых создание, добавление, удаление и удалять элементы управления доступом из объекта `CDacl`.  См. также [AtlGetDacl](../Topic/AtlGetDacl.md) и [AtlSetDacl](../Topic/AtlSetDacl.md).  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Иерархия наследования  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Пример безопасности](../../top/visual-cpp-samples.md)   
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)