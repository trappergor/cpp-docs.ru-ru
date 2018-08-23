---
title: Класс Platform::COMException | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::COMException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
dev_langs:
- C++
helpviewer_keywords:
- Platform::COMException Class
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f67088d7e40f60922fa2fe03993a280284cbf76e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597004"
---
# <a name="platformcomexception-class"></a>Класс Platform::COMException
Представляет ошибки COM, возникающие при выполнении приложения. COMException — базовый класс для набора предопределенных стандартных исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="members"></a>Участники  
 Класс COMException наследует от класса Object и интерфейсов IException, IPrintable и IEquatable.  
  
 Класс COMException также имеет следующие типы членов.  
  
 **Конструкторы**  
  
|Член|Описание:|  
|------------|-----------------|  
|[COMException](#ctor)|Инициализирует новый экземпляр класса COMException.|  
  
 **Методы**  
  
 Класс COMException наследует методы Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() и ToString() от класса [Platform::Object Class](../cppcx/platform-object-class.md).  
  
 **Свойства**  
  
 Класс COMException имеет следующие свойства.  
  
|Член|Описание:|  
|------------|-----------------|  
|[Exception::HRESULT](#hresult)|Значение HRESULT, соответствующее исключению.|  
|[Exception::Message](#message)|Сообщение с описанием исключения.|  
  
## <a name="derived-exceptions"></a>Производные исключения  
 Следующие предопределенные исключения наследуются от класса COMException. Они отличаются от класса COMException только своими именами, именами своих конструкторов и значениями HRESULT.  
  
|name|Значение HRESULT|Описание:|  
|----------|------------------------|-----------------|  
|COMException|*Определяемое пользователем значение hresult*|Возникает при возвращении неизвестного значения HRESULT после вызова метода COM.|  
|AccessDeniedException|E_ACCESSDENIED|Возникает при запрете доступа к ресурсу или функции.|  
|ChangedStateException|E_CHANGED_STATE|Возникает, если метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Возникает, если COM-класс не зарегистрирован.|  
|DisconnectedException|RPC_E_DISCONNECTED|Возникает, если объект отключен от своих клиентов.|  
|FailureException|E_FAIL|Возникает, если операция завершается неудачно.|  
|InvalidArgumentException|E_INVALIDARG|Вызывается, если один из передаваемых методу аргументов является недопустимым.|  
|InvalidCastException|E_NOINTERFACE|Возникает, если тип не удается привести к другому типу.|  
|NotImplementedException|E_NOTIMPL|Возникает, если метод интерфейса не реализован в классе.|  
|NullReferenceException|E_POINTER|Возникает при попытке разыменовать ссылку на объект NULL.|  
|OperationCanceledException|E_ABORT|Возникает при отмене операции.|  
|OutOfBoundsException|E_BOUNDS|Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.|  
|OutOfMemoryException|E_OUTOFMEMORY|Возникает, если недостаточно памяти для выполнения операции.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

## <a name="ctor"></a> Конструктор COMException::COMException
Инициализирует новый экземпляр класса COMException.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
COMException( int hresult )  
```  
  
### <a name="parameters"></a>Параметры  
 hresult  
 HRESULT ошибки, представляемый этим исключением.  
  


## <a name="hresult"></a> COMException::HRESULT-свойство
Значение HRESULT, соответствующее исключению.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## <a name="property-value"></a>Значение свойства  
 Значение HRESULT, задающее ошибку.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения об интерпретации значения HRESULT см. в разделе [структуры из кодов ошибок модели COM](http://go.microsoft.com/fwlink/p/?LinkId=262045).  

## <a name="message"></a> COMException::Message-свойство
Сообщение с описанием исключения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:property String^ Message {    String^ get();}  
```  
  
### <a name="property-value"></a>Значение свойства  
 Описание исключения.  
    

## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)