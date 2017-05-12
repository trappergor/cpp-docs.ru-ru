---
title: "Класс значения Platform::Guid | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Guid - структура"
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Класс значения Platform::Guid
Представляет тип [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) в системе типов среды выполнения Windows.  
  
## Синтаксис  
  
```cpp  
public value struct Guid  
```  
  
## Участники  
 Структура Guid имеет методы Equals\(\), GetHashCode\(\) и ToString\(\), производные от [Класс Platform::Object](../cppcx/platform-object-class.md), и метод GetTypeCode\(\), производный от  [Класс Platform::Type](../cppcx/platform-type-class.md). У структуры Guid также имеются следующие члены.  
  
|Член|Описание|  
|----------|--------------|  
|Guid|Инициализирует новый экземпляр структуры Guid.|  
|operator\=\=|Оператор равенства.|  
|operator\!\=|Оператор неравенства.|  
|operator\(\)|Преобразует Guid в GUID.|  
  
## Заметки  
 Пример создания новой структуры Platform::Guid с использованием функции Windows [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx) см. в разделе [Компонент WinRT: как создать GUID?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)