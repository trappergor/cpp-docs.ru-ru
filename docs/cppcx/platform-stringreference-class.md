---
title: "Класс Platform::StringReference | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::StringReference
Тип оптимизации, который можно использовать для передачи строковых данных из входных параметров `Platform::String^` в другие методы с минимальным числом операций копирования.  
  
## Синтаксис  
  
```cpp  
class StringReference  
```  
  
## Заметки  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор StringReference::StringReference](../cppcx/stringreference-stringreference-constructor.md)|Два конструктора для создания экземпляров `StringReference`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод StringReference::Data](../cppcx/stringreference-data-method.md)|Возвращает строковые данные как массив значений char16.|  
|[Метод StringReference::Length](../cppcx/stringreference-length-method.md)|Возвращает число символов в строке.|  
|[Метод StringReference::GetHSTRING](../cppcx/stringreference-gethstring-method.md)|Возвращает строковые данные как HSTRING.|  
|[Метод StringReference::GetString](../cppcx/stringreference-getstring-method.md)|Возвращает строковые данные как `Platform::String^`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|`StringReference::operator=`|Присваивает `StringReference` новому экземпляру `StringReference`.|  
|`StringReference::operator()`|Преобразует `StringReference` в `Platform::String^`.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Platform::StringReference Class](../cppcx/platform-stringreference-class.md)