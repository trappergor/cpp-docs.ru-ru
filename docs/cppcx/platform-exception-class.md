---
title: "Класс Platform::Exception | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
dev_langs:
- C++
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51df721524fa871b28cc7e4bcb088d4a82a0d1ad
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformexception-class"></a>Класс Platform::Exception
Представляет ошибки, происходящие во время выполнения приложения. Пользовательские классы исключений не могут быть производными от класса `Platform::Exception`. Если требуется пользовательское исключение, можно использовать класс `Platform::COMException` и указать относящееся к приложению значение HRESULT.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="members"></a>Участники  
 Класс `Exception` наследуется от класса `Object` и интерфейсов `IException`, `IPrintable`и `IEquatable` .  
  
 Класс `Exception` имеет также следующие типы членов.  
  
### <a name="constructors"></a>Конструкторы  
  
|Член|Описание:|  
|------------|-----------------|  
|[Exception::Exception](#ctor)|Инициализирует новый экземпляр класса `Exception`.|  
  
### <a name="methods"></a>Методы  
 Класс `Exception` наследует методы `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()`и `ToString()` из [Platform::Object Class](../cppcx/platform-object-class.md). Класс `Exception` содержит также следующий метод.  
  
|Член|Описание:|  
|------------|-----------------|  
|[Exception::CreateException](#createexception)|Создает исключение, представляющее указанное значение HRESULT.|  
  
### <a name="properties"></a>Свойства  
 Класс Exception также содержит следующие свойства.  
  
|Член|Описание:|  
|------------|-----------------|  
|[Exception::HResult](#hresult)|Значение HRESULT, соответствующее исключению.|  
|[Exception::Message](#message)|Сообщение с описанием исключения. Это значение доступно только для чтения, его нельзя изменить после создания `Exception` .|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

## <a name="createexception"></a> Exception::createexception-метод
Создает Platform::Exception^ из указанного значения HRESULT.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
### <a name="parameters"></a>Параметры  
 hr  
 Значение HRESULT, которое, как правило, получается из вызова метода COM. Если значение равно 0, что эквивалентно S_OK, этот метод создает [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) поскольку методы COM, которые завершились успешно, не должны возвращать исключения.  
  
 сообщение  
 Строка с описанием ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исключение, представляющее HRESULT ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для создания исключения из значения HRESULT, возвращаемого, например, из вызова интерфейса COM. Можно использовать перегруженный метод, принимающий параметр String^, чтобы предоставить пользовательское сообщение.  
  
 Это настоятельно рекомендуется использовать CreateException для создания строго типизированного исключения, а не создавать [Platform::COMException](../cppcx/platform-comexception-class.md) , просто содержит значение HRESULT.  
  


## <a name="ctor"></a>  Exception::Exception-конструктор
Инициализирует новый экземпляр класса Exception.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
Exception(int32 hresult)  
Exception(int32 hresult, ::Platform::String^ message)  
```  
  
### <a name="parameters"></a>Параметры  
 `hresult`  
 HRESULT ошибки, представляемый этим исключением.  
  
 `message`  
 Задаваемое пользователем сообщение (например, текст рекомендаций), связанное с исключением. В общем случае следует выбирать вторую перегрузку, чтобы предоставить максимально подробное описание того, как и почему произошла конкретная ошибка.  
  


## <a name="hresult"></a>  Exception::HRESULT-свойство
Значение HRESULT, соответствующее исключению.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## <a name="property-value"></a>Значение свойства  
 Значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Большинство исключений создаются как ошибки модели COM, которые возвращаются в виде значений HRESULT. C++/CX преобразует эти значения в объекты Platform::Exception^, и это свойство сохраняет значение исходного кода ошибки.  
  


## <a name="message"></a> Свойство Exception::Message
Сообщение с описанием ошибки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:property String^ Message;  
```  
  
## <a name="property-value"></a>Значение свойства  
 В исключениях, создаваемых в среде выполнения Windows, это предоставляемое системой описание ошибки.  
  
### <a name="remarks"></a>Примечания  
 В Windows 8 это свойство доступно только для чтения, так как в этой версии среды выполнения Windows исключения передаются через интерфейс ABI только в качестве значения HRESULT. В Windows 8.1 через интерфейс ABI передается более подробная информация об исключениях, и можно задать пользовательское сообщение, к которому другие компоненты могут обращаться программным образом. Дополнительные сведения см. в разделе [исключения (C + +/ CX)](../cppcx/exceptions-c-cx.md).  
  

  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)