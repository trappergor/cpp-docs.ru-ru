---
title: "Метод WeakReference::Resolve (пространство имен Platform) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::Resolve"
ms.assetid: 78bbcadd-89d0-4863-a4e8-1d84040eed7d
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод WeakReference::Resolve (пространство имен Platform)
Возвращает дескриптор для исходного класса ссылок или `nullptr`, если объект больше не существует.  
  
## Синтаксис  
  
```vb  
  
template<typename T>  
T^ Resolve() const  
```  
  
#### Параметры  
  
## Значение свойства, возвращаемое значение  
 Дескриптор класс ссылок, с которым ранее был связан объект WeakReference, или значение nullptr.  
  
## Заметки  
  
## Пример  
 Это описание для примера кода.  
  
```  
  
Bar^ bar = ref new Bar(); //use bar... if (bar != nullptr) { WeakReference wr(bar); Bar^ newReference = wr.Resolve<Bar>(); }  
```  
  
 Обратите внимание, что параметр типа — T, а не T^.  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)