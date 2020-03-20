---
title: Операция safe_cast (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
ms.openlocfilehash: 42e141caed720aa29cf918a2bdf69d9a2c4203dc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544642"
---
# <a name="safe_cast-ccli-and-ccx"></a>Операция safe_cast (C++/CLI и C++/CX)

В случае успешного выполнения операция **safe_cast** возвращает указанное выражение как указанный тип. В противном случае вызывается исключение `InvalidCastException`.

## <a name="all-runtimes"></a>Все среды выполнения

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

### <a name="syntax"></a>Синтаксис

```cpp
[default]:: safe_cast< type-id >( expression )
```

## <a name="windows-runtime"></a>Среда выполнения Windows

Операция **safe_cast** позволяет изменить тип указанного выражения. В ситуациях, где вы полностью рассчитываете на возможность преобразования переменной или параметра в определенный тип, можно использовать **safe_cast** без блока **try-catch** для обнаружения ошибок программирования во время разработки. Дополнительные сведения см. в статье [Приведение (C++/CX)](../cppcx/casting-c-cx.md).

### <a name="syntax"></a>Синтаксис

```cpp
[default]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>Параметры

*type-id*<br/>
Тип, в который следует преобразовать *выражение*. Дескриптор ссылки или типа значения, тип значения или отслеживаемая ссылка на ссылку или тип значения.

*expression*<br/>
Выражение, которое оценивается в дескрипторе ссылки или типа значения, типе значения или отслеживаемой ссылке на ссылку или тип значения.

### <a name="remarks"></a>Примечания

**safe_cast** создает исключение `InvalidCastException`, если оно не может преобразовать *выражение* в тип, указанный в *типе-ID*. Чтобы перехватить `InvalidCastException`, укажите параметр компилятора [/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md) и используйте инструкцию **try/catch** .

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

### <a name="examples"></a>Примеры

В следующем примере кода демонстрируется использование **safe_cast** со средой выполнения Windows.

```cpp
// safe_cast_ZW.cpp
// compile with: /ZW /EHsc

using namespace default;
using namespace Platform;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main(Array<String^>^ args) {
   I1^ i1 = ref new X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.
   }
   catch(InvalidCastException^ ic) {
   wprintf(L"Caught expected exception: %s\n", ic->Message);
   }
}
```

```Output
Caught expected exception: InvalidCastException
```

## <a name="common-language-runtime"></a>Среда CLR

Операция **safe_cast** позволяет изменить тип выражения и создать проверяемый код MSIL.

### <a name="syntax"></a>Синтаксис

```cpp
[cli]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>Параметры

*type-id*<br/>
Дескриптор ссылки или типа значения, тип значения или отслеживаемая ссылка на ссылку или тип значения.

*expression*<br/>
Выражение, которое оценивается в дескрипторе ссылки или типа значения, типе значения или отслеживаемой ссылке на ссылку или тип значения.

### <a name="remarks"></a>Примечания

Выражение `safe_cast<`*type-id*`>(`*expression*`)` преобразует *выражение* операнда в объект с типом *type-id*.

Компилятор будет принимать [static_cast](../cpp/static-cast-operator.md) в большинстве мест, где будет принимать **safe_cast**.  Однако **safe_cast** гарантированно создает проверяемый код MSIL, тогда как **static_cast** может создать непроверяемый MSIL.  Дополнительные сведения о проверяемом коде см. в статьях [Чистый и проверяемый код (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) и [Peverify.exe (средство PEVerify)](/dotnet/framework/tools/peverify-exe-peverify-tool).

Как и **static_cast**, **safe_cast** вызывает заданные пользователем преобразования.

Дополнительные сведения о приведениях см. в разделе [Операторы приведения](../cpp/casting-operators.md).

**safe_cast** не применяет **const_cast** (отвергает **const**).

**safe_cast** находится в пространстве имен CLI.  Дополнительные сведения см. в статье [Platform, default, and cli Namespaces (C++/CLI and C++/CX)](platform-default-and-cli-namespaces-cpp-component-extensions.md) (Пространства имен Platform, default и cli (C++/CLI и C++/CX)).

Дополнительные сведения о **safe_cast** см. в следующих статьях.

- [Приведение в стиле C с использованием параметра /clr (C++/CLI)](c-style-casts-with-clr-cpp-cli.md)

- [Практическое руководство. Использование safe_cast в C++/CLI](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

Пример, когда компилятор не будет принимать **static_cast**, но будет принимать **safe_cast**, —приведения между несвязанными типами интерфейса.  При использовании **safe_cast** компилятор не будет выдавать ошибку преобразования и будет выполнять проверку во время выполнения, чтобы увидеть, возможно ли приведение.

```cpp
// safe_cast.cpp
// compile with: /clr
using namespace System;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main() {
   I1^ i1 = gcnew X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type
   }
   catch(InvalidCastException^) {
      Console::WriteLine("Caught expected exception");
   }
}
```

```Output
Caught expected exception
```

## <a name="see-also"></a>См. также:

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
