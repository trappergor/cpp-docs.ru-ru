---
title: "CComVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComVariant"
  - "ATL::CComVariant"
  - "CComVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComVariant class"
  - "VARIANT macro"
  - "VARIANT macro, ATL - библиотека"
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CComVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс создает программу\-оболочку тип `VARIANT`, предоставляя элемента, указывающий тип хранимых данных.  
  
## Синтаксис  
  
```  
  
class CComVariant : public tagVARIANT  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComVariant::CComVariant](../Topic/CComVariant::CComVariant.md)|Конструктор.|  
|[CComVariant::~CComVariant](../Topic/CComVariant::~CComVariant.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComVariant::Attach](../Topic/CComVariant::Attach.md)|Вложение **VARIANT** к объекту `CComVariant`.|  
|[CComVariant::ChangeType](../Topic/CComVariant::ChangeType.md)|Преобразует объект `CComVariant` в новый тип.|  
|[CComVariant::Clear](../Topic/CComVariant::Clear.md)|Удаляет объект `CComVariant`.|  
|[CComVariant::Copy](../Topic/CComVariant::Copy.md)|Копирует **VARIANT** к объекту `CComVariant`.|  
|[CComVariant::CopyTo](../Topic/CComVariant::CopyTo.md)|Копирует содержимое объекта `CComVariant`.|  
|[CComVariant::Detach](../Topic/CComVariant::Detach.md)|Наконец **VARIANT** удаляет узел из объекта `CComVariant`.|  
|[CComVariant::GetSize](../Topic/CComVariant::GetSize.md)|Возвращает размер в байтах `CComVariant` содержимого объекта.|  
|[CComVariant::ReadFromStream](../Topic/CComVariant::ReadFromStream.md)|Загружает **VARIANT** из потока.|  
|[CComVariant::SetByRef](../Topic/CComVariant::SetByRef.md)|Инициализирует объект `CComVariant` и задает участника **vt** к **VT\_BYREF**.|  
|[CComVariant::WriteToStream](../Topic/CComVariant::WriteToStream.md)|Сохраняет узел **VARIANT** в поток.|  
  
### Открытые операторы  
  
|||  
|-|-|  
|[CComVariant::operator \<](../Topic/CComVariant::operator%20%3C.md)|Указывает, является ли объект `CComVariant`, чем указанное **VARIANT**.|  
|[CComVariant::operator \>](../Topic/CComVariant::operator%20%3E.md)|Указывает, является ли объект `CComVariant` превышает указанное **VARIANT**.|  
|[оператор\! \=](../Topic/CComVariant::operator%20!=.md)|Указывает, равен ли указанный объект `CComVariant` не **VARIANT**.|  
|[оператор \=](../Topic/CComVariant::operator%20=.md)|Присвоить значение объекта `CComVariant`.|  
|[\=\= \- оператор](../Topic/CComVariant::operator%20==.md)|Указывает, равен ли указанный объект `CComVariant`**VARIANT**.|  
  
## Заметки  
 Создает `CComVariant` программу\-оболочку тип `VARIANT and VARIANTARG`, который состоит из объединения и членов, указывающее тип данных, хранимых в соединении.  **VARIANT** s обычно используется в автоматизации.  
  
 `CComVariant` является производным от типа **VARIANT** поэтому его можно использовать везде, где можно использовать **VARIANT**.  Можно, например, использовать макрос **V\_VT** для извлечения тип `CComVariant` или доступа к члену **vt** непосредственно как можно с **VARIANT**.  
  
## Иерархия наследования  
 `tagVARIANT`  
  
 `CComVariant`  
  
## Требования  
 **Header:**  atlcomcli.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)