---
title: "Интерфейс Platform::IBoxArray | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBoxArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IBoxArray"
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Интерфейс Platform::IBoxArray
`IBoxArray` является оболочкой для массивов типов значений, передаваемых через двоичный интерфейс приложений \(ABI\) или хранящихся в коллекциях элементов `Platform::Object^`, таких как коллекции в элементах управления XAML.  
  
## Синтаксис  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### Параметры  
 `T`  
 Тип упакованного значение в каждом элементе массива.  
  
## Заметки  
 `IBoxArray` является именем [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) для `Windows::Foundation::IReferenceArray`.  
  
## Члены  
 Интерфейс `IBoxArray` наследует от интерфейса `IValueType`. Интерфейс `IBoxArray` также содержит следующие члены:  
  
|Метод|Описание|  
|-----------|--------------|  
|Значение|Возвращает распакованный массив, который ранее хранился в этом экземпляре `IBoxArray`.|  
  
## См. также  
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)