---
title: "CSid Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSid"
  - "ATL::CSid"
  - "ATL.CSid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSid class"
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CSid Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры `SID` \(идентификатор безопасности\).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CSid  
  
```  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CSid::CSidArray](../Topic/CSid::CSidArray.md)|Массив объектов `CSid`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSid::CSid](../Topic/CSid::CSid.md)|Конструктор.|  
|[CSid::~CSid](../Topic/CSid::~CSid.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSid::AccountName](../Topic/CSid::AccountName.md)|Возвращает имя учетной записи, связанной с объектом `CSid`.|  
|[CSid::Domain](../Topic/CSid::Domain.md)|Возвращает имя домена, связанного с объектом `CSid`.|  
|[CSid::EqualPrefix](../Topic/CSid::EqualPrefix.md)|Проверяет префиксы `SID` \(идентификатор безопасности\) на равенство.|  
|[CSid::GetLength](../Topic/CSid::GetLength.md)|Возвращает длину объекта `CSid`.|  
|[CSid::GetPSID](../Topic/CSid::GetPSID.md)|Возвращает указатель на структуру `SID`.|  
|[CSid::GetPSID\_IDENTIFIER\_AUTHORITY](../Topic/CSid::GetPSID_IDENTIFIER_AUTHORITY.md)|Возвращает указатель на структуру **SID\_IDENTIFIER\_AUTHORITY**.|  
|[CSid::GetSubAuthority](../Topic/CSid::GetSubAuthority.md)|Возвращает указанный subauthority в структуре **SID** .|  
|[CSid::GetSubAuthorityCount](../Topic/CSid::GetSubAuthorityCount.md)|Возвращает количество subauthority.|  
|[CSid::IsValid](../Topic/CSid::IsValid.md)|Проверяет объект `CSid` на допустимость.|  
|[CSid::LoadAccount](../Topic/CSid::LoadAccount.md)|Обновляет объект `CSid` заданное имя учетной записи, а домен или существующая структура `SID`.|  
|[CSid::Sid](../Topic/CSid::Sid.md)|Возвращает строку идентификатора.|  
|[CSid::SidNameUse](../Topic/CSid::SidNameUse.md)|Возвращает описание состояния объекта `CSid`.|  
  
### Операторы  
  
|||  
|-|-|  
|[оператор \=](../Topic/CSid::operator%20=.md)|Оператор присваивания.|  
|[идентификатор безопасности const оператора \*](../Topic/CSid::operator%20const%20SID%20*.md)|Приводит объект `CSid` на указатель на структуру `SID`.|  
  
### Глобальные операторы  
  
|||  
|-|-|  
|[\=\= \- оператор](../Topic/CSid::operator%20==.md)|Тесты 2 объекта дескриптора безопасности для равенства|  
|[оператор\! \=](../Topic/CSid::operator%20!=.md)|Тесты 2 объекта дескриптора безопасности на неравенство|  
|[оператор \<](../Topic/CSid::operator%20%3C.md)|Сравнивает относительное значение 2 объектов дескриптора безопасности.|  
|[оператор \>](../Topic/CSid::operator%20%3E.md)|Сравнивает относительное значение 2 объектов дескриптора безопасности.|  
|[\<\= оператора](../Topic/CSid::operator%20%3C=.md)|Сравнивает относительное значение 2 объектов дескриптора безопасности.|  
|[\>\= оператора](../Topic/CSid::operator%20%3E=.md)|Сравнивает относительное значение 2 объектов дескриптора безопасности.|  
  
## Заметки  
 Структура `SID` переменной длины, структура, используемая для уникальной идентификации пользователей или групп.  
  
 Приложения не должны непосредственно изменять структуру `SID` вместо этого он использует предоставленные методы в этом класс\-оболочке.  См. также [AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md), [AtlSetGroupSid](../Topic/AtlSetGroupSid.md), [AtlGetGroupSid](../Topic/AtlGetGroupSid.md) и [AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md).  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Пример безопасности](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)   
 [Operators Alphabetical Reference](../../atl/reference/atl-operators.md)