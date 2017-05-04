---
title: "Метод Object::ToString (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::ToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Платформа, Object::ToString"
ms.assetid: 229dbf1c-cb43-4ed2-a1c5-a1f36b22a7ea
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Object::ToString (C++/CX)
Возвращает строку, представляющую текущий объект.  
  
## Синтаксис  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
## Возвращаемое значение  
 Строка, представляющая текущий объект. Этот метод можно переопределить, чтобы ссылочный класс или структура содержали пользовательскую строку сообщения:  
  
```cpp  
public ref class Tree sealed { public: Tree(){} virtual Platform::String^ ToString()override { return "I’m a Tree"; }; };  
```  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Object](../cppcx/platform-object-class.md)