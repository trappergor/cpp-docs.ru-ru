---
title: "CSecurityDesc Class | Microsoft Docs"
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
  - "ATL::CSecurityDesc"
  - "ATL.CSecurityDesc"
  - "CSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityDesc class"
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSecurityDesc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры **SECURITY\_DESCRIPTOR**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CSecurityDesc  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSecurityDesc::CSecurityDesc](../Topic/CSecurityDesc::CSecurityDesc.md)|Конструктор.|  
|[CSecurityDesc::~CSecurityDesc](../Topic/CSecurityDesc::~CSecurityDesc.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSecurityDesc::FromString](../Topic/CSecurityDesc::FromString.md)|Преобразование строкового формата в допустимый дескриптор безопасности, функциональный дескриптор безопасности.|  
|[CSecurityDesc::GetControl](../Topic/CSecurityDesc::GetControl.md)|Извлекает управляющая сведения из дескриптора безопасности.|  
|[CSecurityDesc::GetDacl](../Topic/CSecurityDesc::GetDacl.md)|Извлекает данные списка управления доступом на уровне пользователей \(DACL\) из дескриптора безопасности.|  
|[CSecurityDesc::GetGroup](../Topic/CSecurityDesc::GetGroup.md)|Извлекает данные первичной группы из дескриптора безопасности.|  
|[CSecurityDesc::GetOwner](../Topic/CSecurityDesc::GetOwner.md)|Извлекает из informaton владельцем дескриптора безопасности.|  
|[CSecurityDesc::GetPSECURITY\_DESCRIPTOR](../Topic/CSecurityDesc::GetPSECURITY_DESCRIPTOR.md)|Возвращает указатель на структуру **SECURITY\_DESCRIPTOR**.|  
|[CSecurityDesc::GetSacl](../Topic/CSecurityDesc::GetSacl.md)|Извлекает данные системного списка управления доступом \(sacl\) из дескриптора безопасности.|  
|[CSecurityDesc::IsDaclAutoInherited](../Topic/CSecurityDesc::IsDaclAutoInherited.md)|Определяет, если список управления доступом на уровне пользователей настроено, чтобы поддерживать автоматическое распространение.|  
|[CSecurityDesc::IsDaclDefaulted](../Topic/CSecurityDesc::IsDaclDefaulted.md)|Определяет, если дескриптор безопасности настройки по умолчанию DACL.|  
|[CSecurityDesc::IsDaclPresent](../Topic/CSecurityDesc::IsDaclPresent.md)|Определяет, если дескриптор безопасности содержит список DACL.|  
|[CSecurityDesc::IsDaclProtected](../Topic/CSecurityDesc::IsDaclProtected.md)|Определяет, если список управления доступом на уровне пользователей настроено для предотвращения изменения.|  
|[CSecurityDesc::IsGroupDefaulted](../Topic/CSecurityDesc::IsGroupDefaulted.md)|Определяет, если идентификатор безопасности группы дескриптора безопасности \(sid\) был установлен по умолчанию.|  
|[CSecurityDesc::IsOwnerDefaulted](../Topic/CSecurityDesc::IsOwnerDefaulted.md)|Определяет, если идентификатор безопасности владельца дескриптора безопасности был установлен по умолчанию.|  
|[CSecurityDesc::IsSaclAutoInherited](../Topic/CSecurityDesc::IsSaclAutoInherited.md)|Определяет, если системный список управления доступом настроить для поддержки автоматическое распространение.|  
|[CSecurityDesc::IsSaclDefaulted](../Topic/CSecurityDesc::IsSaclDefaulted.md)|Определяет, если дескриптор безопасности настройки по умолчанию системным списком управления доступом.|  
|[CSecurityDesc::IsSaclPresent](../Topic/CSecurityDesc::IsSaclPresent.md)|Определяет, если дескриптор безопасности содержит системный список управления доступом.|  
|[CSecurityDesc::IsSaclProtected](../Topic/CSecurityDesc::IsSaclProtected.md)|Определяет, если системный список управления доступом настроить для предотвращения изменения.|  
|[CSecurityDesc::IsSelfRelative](../Topic/CSecurityDesc::IsSelfRelative.md)|Определяет, если дескриптор безопасности в собственный\- относительного формате.|  
|[CSecurityDesc::MakeAbsolute](../Topic/CSecurityDesc::MakeAbsolute.md)|Этот метод вызывается для преобразования дескриптор безопасности абсолютного формат.|  
|[CSecurityDesc::MakeSelfRelative](../Topic/CSecurityDesc::MakeSelfRelative.md)|Этот метод вызывается для преобразования относительного собственный\- дескриптор безопасности в формат.|  
|[CSecurityDesc::SetControl](../Topic/CSecurityDesc::SetControl.md)|Задает биты элемента управления дескриптора безопасности.|  
|[CSecurityDesc::SetDacl](../Topic/CSecurityDesc::SetDacl.md)|Задает информацию в списке управления доступом на уровне пользователей.  Если список управления доступом на уровне пользователей уже присутствует в дескрипторе безопасности, оно заменено.|  
|[CSecurityDesc::SetGroup](../Topic/CSecurityDesc::SetGroup.md)|Устанавливает данные первичной группы абсолютного дескриптора безопасности формата, заменив все данные первичной группы уже присутствующие.|  
|[CSecurityDesc::SetOwner](../Topic/CSecurityDesc::SetOwner.md)|Задает сведения о владельце абсолютного дескриптора безопасности формата, заменяя любой данных о владельце уже существует.|  
|[CSecurityDesc::SetSacl](../Topic/CSecurityDesc::SetSacl.md)|Задает информацию в системном списке управления доступом.  Если системный список управления доступом уже присутствует в дескрипторе безопасности, он заменить.|  
|[CSecurityDesc::ToString](../Topic/CSecurityDesc::ToString.md)|Дескриптор безопасности преобразования в строковый формат.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSecurityDesc::operator const SECURITY\_DESCRIPTOR \*](../Topic/CSecurityDesc::operator%20const%20SECURITY_DESCRIPTOR%20*.md)|Возвращает указатель на структуру **SECURITY\_DESCRIPTOR**.|  
|[CSecurityDesc::operator \=](../Topic/CSecurityDesc::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 Структура **SECURITY\_DESCRIPTOR** содержит сведения о безопасности, связанной с объектом.  Приложения используют эту структуру для задания и запросы состояния безопасности объекта.  См. также [AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md).  
  
 Приложения не должны непосредственно изменять структуру **SECURITY\_DESCRIPTOR**, а вместо этого следует использовать методы, предоставленные класса.  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Пример безопасности](../../top/visual-cpp-samples.md)   
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)