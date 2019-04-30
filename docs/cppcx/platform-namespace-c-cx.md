---
title: Пространство имен Platform (C++/CX)
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- Platform/Platform
helpviewer_keywords:
- Platform Namespace (C++/CX)
ms.assetid: b160e822-d424-43d2-ba60-57b0e81f259c
ms.openlocfilehash: ffbfdde1a9c610f6bcb2356a26acb2b85ed9624a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345776"
---
# <a name="platform-namespace-ccx"></a>Пространство имен Platform (C++/CX)

Содержит встроенные типы, совместимые со средой выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
using namespace Platform;
```

### <a name="members"></a>Участники

**Атрибуты**

Пространство имен Platform содержит атрибуты, классы, перечисления, интерфейсы и структуры. Platform также содержит вложенные пространства имен.

|Атрибут|Описание|
|---------------|-----------------|
|Флаги|Указывает, что перечисление может обрабатываться как битовое поле (т. е. набор флагов).|
|MTAThread|Указывает, что потоковая модель для приложения является многопотоковым подразделением (MTA).|
|STAThread|Указывает, что потоковая модель для приложения является однопотоковым подразделением (STA).|

**Классы**

Пространство имен Platform содержит следующие классы.

|Класс|Описание|
|-----------|-----------------|
|[Класс Platform::AccessDeniedException](../cppcx/platform-accessdeniedexception-class.md)|Возникает при запрете доступа к ресурсу или функции.|
|[Класс Platform::Agile](../cppcx/platform-agile-class.md)|Представляет объект, отличный от Agile, как объект Agile.|
|[Класс Platform::Array](../cppcx/platform-array-class.md)|Представляет одномерный изменяемый массив.|
|[Класс Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)|Представляет массив, инициализация которого оптимизирована, чтобы свести к минимуму число операций копирования.|
|[Класс Platform::Box](../cppcx/platform-box-class.md)|Используется для объявления упакованного типа, который инкапсулирует тип значений, например Windows::Foundation::DateTime или int64, когда этот тип передается через двоичный интерфейс приложения (ABI) или сохраняется в переменной типа [Platform::Object^](../cppcx/platform-object-class.md).|
|[Класс Platform::ChangedStateException](../cppcx/platform-changedstateexception-class.md)|Возникает, если метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.|
|[Класс Platform::ClassNotRegisteredException](../cppcx/platform-classnotregisteredexception-class.md)|Возникает, если COM-класс не зарегистрирован.|
|[Класс Platform::COMException](../cppcx/platform-comexception-class.md)|Представляет исключение, создаваемое при возвращении нераспознанного значения после вызова метода COM.|
|[Класс Platform::Delegate](../cppcx/platform-delegate-class.md)|Представляет сигнатуру функции обратного вызова.|
|[Класс Platform::DisconnectedException](../cppcx/platform-disconnectedexception-class.md)|Объект отключен от своих клиентов.|
|[Класс Platform::Exception](../cppcx/platform-exception-class.md)|Представляет ошибки, происходящие во время выполнения приложения. Базовый класс для исключений.|
|[Класс Platform::FailureException](../cppcx/platform-failureexception-class.md)|Вызывается, если операция вызвала сбой. Эквивалентно E_FAIL HRESULT.|
|[Класс значения Platform::Guid](../cppcx/platform-guid-value-class.md)|Представляет идентификатор GUID в системе типов среды выполнения Windows.|
|[Класс Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md)|Вызывается, если один из передаваемых методу аргументов является недопустимым.|
|[Класс Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md)|Возникает в случаях недопустимого приведения или явного преобразования.|
|[Класс Platform::MTAThreadAttribute](../cppcx/platform-mtathreadattribute-class.md)|Указывает, что потоковая модель для приложения является многопотоковым подразделением (MTA).|
|[Класс Platform::NotImplementedException](../cppcx/platform-notimplementedexception-class.md)|Возникает, если метод интерфейса не реализован в классе.|
|[Класс Platform::NullReferenceException](../cppcx/platform-nullreferenceexception-class.md)|Возникает при попытке разыменовать ссылку на объект NULL.|
|[Класс Platform::Object](../cppcx/platform-object-class.md)|Базовый класс, который обеспечивает общее поведение.|
|[Класс Platform::ObjectDisposedException](../cppcx/platform-objectdisposedexception-class.md)|Вызывается при выполнении операции над ликвидированным объектом.|
|[Класс Platform::OperationCanceledException](../cppcx/platform-operationcanceledexception-class.md)|Возникает при отмене операции.|
|[Класс Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md)|Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.|
|[Класс Platform::OutOfMemoryException](../cppcx/platform-outofmemoryexception-class.md)|Возникает, если недостаточно памяти для выполнения операции.|
|[Класс Platform::STAThreadAttribute](../cppcx/platform-stathreadattribute-class.md)|Указывает, что потоковая модель для приложения является однопотоковым подразделением (STA).|
|[Класс Platform::String](../cppcx/platform-string-class.md)|Упорядоченная коллекция символов Юникода, используемая для представления текста.|
|[Класс Platform::StringReference](../cppcx/platform-stringreference-class.md)|Обеспечивает доступ к буферам строк с минимальной нагрузкой копирования.|
|[Класс Platform::Type](../cppcx/platform-type-class.md)|Указывает встроенный тип посредством перечисления категорий.|
|[Класс Platform::ValueType](../cppcx/platform-valuetype-class.md)|Базовый класс для экземпляров типов значений.|
|[Класс Platform::WeakReference](../cppcx/platform-weakreference-class.md)|Предоставляет гибкую ссылку на объекты ссылочного класса, которая не увеличивает число ссылок.|
|[Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)|Представляет доступный только для записи одномерный массив, используемый в качестве входного параметра в методах, реализующих шаблон FillArray.|
|[Класс Platform::WrongThreadException](../cppcx/platform-wrongthreadexception-class.md)|Вызывается, если поток выполняет вызов посредством указателя на интерфейс для прокси-объекта, который не принадлежит к подразделению потока.|

**Реализации интерфейсов**

Пространство имен Platform определяет следующие интерфейсы.

|Интерфейс|Описание|
|---------------|-----------------|
|[Интерфейс Platform::IBox](../cppcx/platform-ibox-interface.md)|Используется для передачи типов значений в функции, параметры которых имеют тип Platform::Object^.|
|[Интерфейс Platform::IBoxArray](../cppcx/platform-iboxarray-interface.md)|Интерфейс, используемый для передачи массивов типов значений в функции, параметры которых имеют тип Platform::Array.|
|[Интерфейс Platform::IDisposable](../cppcx/platform-idisposable-interface.md)|Используется для освобождения неуправляемых ресурсов.|

**Перечисления**

Пространство имен Platform содержит следующие перечисления.

|Интерфейс|Описание|
|---------------|-----------------|
|[Перечисление Platform::CallbackContext](../cppcx/platform-callbackcontext-enumeration.md)|Перечисление, используемое в качестве параметра конструктора делегата. Определяет, следует ли маршалировать обратный вызов в исходный поток или в поток вызывающего объекта.|
|[Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md)|Указывает категорию чисел, представляющую встроенный тип.|

**Структуры**

Пространство имен Platform содержит следующие структуры.

|Структура|Описание|
|---------------|-----------------|
|[Класс Platform::Enum](../cppcx/platform-enum-class.md)|Представляет константу с именем.|
|[Класс значения Platform::Guid](../cppcx/platform-guid-value-class.md)|Представляет идентификатор GUID.|
|[Класс значений Platform::IntPtr](../cppcx/platform-intptr-value-class.md)|Указатель со знаком, размер которого соответствует платформе (32-разрядной или 64-разрядной).|
|[Класс значений Platform::SizeT](../cppcx/platform-sizet-value-class.md)|Тип данных без знака, используемый для представления размера объекта.|
|[Класс значений Platform::UIntPtr](../cppcx/platform-uintptr-value-class.md)|Указатель без знака, размер которого соответствует платформе (32-разрядной или 64-разрядной).|

## <a name="see-also"></a>См. также

[Пространство имен Platform::Collections](../cppcx/platform-collections-namespace.md)<br/>
[Пространство имен Platform::Runtime::CompilerServices](../cppcx/platform-runtime-compilerservices-namespace.md)<br/>
[Пространство имен Platform::Runtime::InteropServices](../cppcx/platform-runtime-interopservices-namespace.md)<br/>
[Пространство имен Platform::Metadata](../cppcx/platform-metadata-namespace.md)
