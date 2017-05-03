---
title: "Метод Object::GetHashCode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetHashCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Платформа, Object::GetHashCode"
ms.assetid: 403a60e9-be1d-4702-b14d-27fa4b2a043b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Object::GetHashCode
Возвращает значение идентификатора [IUnknown](../atl/iunknown.md)\* для этого экземпляра, если это COM\-объект, или вычисляемое хэш\-значение, если это не COM\-объект.  
  
## Синтаксис  
  
```cpp  
public:int GetHashCode()  
```  
  
## Возвращаемое значение  
 Числовое значение, которое однозначно идентифицирует этот объект.  
  
## Заметки  
 Можно использовать GetHashCode для создание ключей объектов в сопоставлениях. Хэш\-коды можно сравнивать с помощью [Метод Object::Equals](../cppcx/object-equals-method.md). Если эта ветвь выполнения кода очень важна, а `GetHashCode` и `Equals` работают недостаточно быстро, можно перейти вниз на соответствующий уровень COM и выполнять сравнение указателей [IUnknown](../atl/iunknown.md) в неуправляемом коде.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Object](../cppcx/platform-object-class.md)