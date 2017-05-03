---
title: "Класс значения Platform::IntPtr | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IntPtr - структура"
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс значения Platform::IntPtr
Представляет указатель или дескриптор числа со знаком, размер которого зависит от платформы \(32\-разрядная или 64\-разрядная\).  
  
## Синтаксис  
  
```cpp  
public value struct IntPtr  
```  
  
## Члены  
 Класс IntPtr имеет следующие члены:  
  
|Член|Описание|  
|----------|--------------|  
|[IntPtr::IntPtr \- конструктор](../cppcx/intptr-intptr-constructor.md)|Инициализирует новый экземпляр класса IntPtr.|  
|[Оператор IntPtr::op\_explicit](../cppcx/intptr-op-explicit-operator.md)|Преобразует указанный параметр в объект IntPtr или указатель на значение IntPtr.|  
|[Метод IntPtr::ToInt32](../cppcx/intptr-toint32-method.md)|Преобразует текущий объект IntPtr в 32\-разрядное целое число.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)