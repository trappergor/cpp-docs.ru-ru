---
title: "Exception::CreateException - метод | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::CreateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::CreateException - метод"
ms.assetid: 70e72bb4-3fec-478d-af3d-9ec8762d2825
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::CreateException - метод
Создает Platform::Exception^ из указанного значения HRESULT.  
  
## Синтаксис  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
## Параметры  
 hr  
 Значение HRESULT, которое, как правило, получается из вызова метода COM. Если значение равно 0, что эквивалентно S\_OK, этот метод создает исключение [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md), поскольку методы COM, которые завершаются успешно, не должны возвращать исключения.  
  
 сообщение  
 Строка с описанием ошибки.  
  
## Возвращаемое значение  
 Исключение, представляющее HRESULT ошибки.  
  
## Заметки  
 Используйте этот метод для создания исключения из значения HRESULT, возвращаемого, например, из вызова интерфейса COM. Можно использовать перегруженный метод, принимающий параметр String^, чтобы предоставить пользовательское сообщение.  
  
 Настоятельно рекомендуется использовать CreateException для создания строго типизированного исключения, а не просто создать [Platform::COMException](../cppcx/platform-comexception-class.md), который просто содержит значение HRESULT.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)