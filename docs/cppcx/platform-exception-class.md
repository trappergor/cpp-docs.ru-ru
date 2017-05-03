---
title: "Класс Platform::Exception | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс Platform::Exception"
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Класс Platform::Exception
Представляет ошибки, происходящие во время выполнения приложения. Пользовательские классы исключений не могут быть производными от класса `Platform::Exception`. Если требуется пользовательское исключение, можно использовать класс `Platform::COMException` и указать относящееся к приложению значение HRESULT.  
  
## Синтаксис  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
## Члены  
 Класс `Exception` наследуется от класса `Object` и интерфейсов `IException`, `IPrintable` и `IEquatable`.  
  
 Класс `Exception` имеет также следующие типы членов.  
  
### Конструкторы  
  
|Член|Описание|  
|----------|--------------|  
|[Exception::Exception \- конструктор](../cppcx/exception-exception-constructor.md)|Инициализирует новый экземпляр класса `Exception`.|  
  
### Методы  
 Класс `Exception` наследует методы `Equals()`, `Finalize()`, `GetHashCode()`, `GetType()`, `MemberwiseClose()` и `ToString()` из [Класс Platform::Object](../cppcx/platform-object-class.md). Класс `Exception` содержит также следующий метод.  
  
|Член|Описание|  
|----------|--------------|  
|[Exception::CreateException \- метод](../cppcx/exception-createexception-method.md)|Создает исключение, представляющее указанное значение HRESULT.|  
  
### Свойства  
 Класс Exception также содержит следующие свойства.  
  
|Член|Описание|  
|----------|--------------|  
|[Exception::HResult \- свойство](../cppcx/exception-hresult-property.md)|Значение HRESULT, соответствующее исключению.|  
|[Свойство Exception::Message](../cppcx/exception-message-property.md)|Сообщение с описанием исключения. Это значение доступно только для чтения, его нельзя изменить после создания `Exception`.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)