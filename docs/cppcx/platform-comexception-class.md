---
title: "Класс Platform::COMException | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс Platform::COMException"
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::COMException
Представляет ошибки COM, возникающие при выполнении приложения. COMException — базовый класс для набора предопределенных стандартных исключений.  
  
## Синтаксис  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
## Члены  
 Класс COMException наследует от класса Object и интерфейсов IException, IPrintable и IEquatable.  
  
 Класс COMException также имеет следующие типы членов.  
  
 **Конструкторы**  
  
|Член|Описание|  
|----------|--------------|  
|`COMException`|Инициализирует новый экземпляр класса COMException.|  
  
 **Методы**  
  
 Класс COMException наследует методы Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) и ToString\(\) от класса [Класс Platform::Object](../cppcx/platform-object-class.md).  
  
 **Свойства**  
  
 Класс COMException имеет следующие свойства.  
  
|Член|Описание|  
|----------|--------------|  
|[Exception::HResult \- свойство](../cppcx/exception-hresult-property.md)|Значение HRESULT, соответствующее исключению.|  
|[Свойство Exception::Message](../cppcx/exception-message-property.md)|Сообщение с описанием исключения.|  
  
## Производные исключения  
 Следующие предопределенные исключения наследуются от класса COMException. Они отличаются от класса COMException только своими именами, именами своих конструкторов и значениями HRESULT.  
  
|Имя|Значение HRESULT|Описание|  
|---------|----------------------|--------------|  
|COMException|*Определяемое пользователем значение hresult*|Возникает при возвращении неизвестного значения HRESULT после вызова метода COM.|  
|AccessDeniedException|E\_ACCESSDENIED|Возникает при запрете доступа к ресурсу или функции.|  
|ChangedStateException|E\_CHANGED\_STATE|Возникает, если метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Возникает, если COM\-класс не зарегистрирован.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|Возникает, если объект отключен от своих клиентов.|  
|FailureException|E\_FAIL|Возникает, если операция завершается неудачно.|  
|InvalidArgumentException|E\_INVALIDARG|Вызывается, если один из передаваемых методу аргументов является недопустимым.|  
|InvalidCastException|E\_NOINTERFACE|Возникает, если тип не удается привести к другому типу.|  
|NotImplementedException|E\_NOTIMPL|Возникает, если метод интерфейса не реализован в классе.|  
|NullReferenceException|E\_POINTER|Возникает при попытке разыменовать ссылку на объект NULL.|  
|OperationCanceledException|E\_ABORT|Возникает при отмене операции.|  
|OutOfBoundsException|E\_BOUNDS|Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.|  
|OutOfMemoryException|E\_OUTOFMEMORY|Возникает, если недостаточно памяти для выполнения операции.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)