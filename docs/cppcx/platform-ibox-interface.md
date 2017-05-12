---
title: "Интерфейс Platform::IBox | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBox"
dev_langs: 
  - "C++"
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Интерфейс Platform::IBox
[Platform::IBox](../cppcx/platform-ibox-interface.md) — это имя C\+\+ для интерфейса `Windows::Foundation::IReference`.  
  
## Синтаксис  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### Параметры  
 `T`  
 Введите запакованное значение.  
  
## Заметки  
 Интерфейс `IBox<T>` в основном используется внутри кода для представления типов значений, допускающих значение null, как описано в разделе [Классы и структуры значения \(C\+\+\/CX\)](../cppcx/value-classes-and-structs-c-cx.md). Этот интерфейс также используется для упаковки типов значений, передаваемых в методы C\+\+, которые принимают параметры типа `Object^`. Можно в явном виде определить входной параметр как `IBox<SomeValueType>`. Пример см. в разделе [Упаковка](../cppcx/boxing-c-cx.md).  
  
## Требования  
  
## Члены  
 Интерфейс `Platform::IBox` наследуется от интерфейса [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md). Интерфейс `IBox` содержит следующие члены:  
  
 **Свойства**  
  
|Метод|Описание|  
|-----------|--------------|  
|Значение|Возвращает распакованное значение, которое ранее хранилось в этом экземпляре `IBox`.|  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)