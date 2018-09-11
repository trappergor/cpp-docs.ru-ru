---
title: safe_cast (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85a27fceabcac9c5fa3b36fae4990da7dcd65deb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222930"
---
# <a name="safecast-c-component-extensions"></a>safe_cast (расширения компонентов C++)

**Safe_cast** операция возвращает указанное выражение как указанный тип, в случае успеха; в противном случае создает `InvalidCastException`.

## <a name="all-runtimes"></a>Все среды выполнения

(Отсутствуют комментарии для этой функции языка, которая применяется во всех средах выполнения.)

### <a name="syntax"></a>Синтаксис

```cpp
[default]:: safe_cast<
type-id
>(
expression
)  
```

## <a name="windows-runtime"></a>Среда выполнения Windows

**safe_cast** позволяет изменить тип заданного выражения. В ситуациях, где вы полностью рассчитываете переменная или параметр, возможность преобразования определенного типа, можно использовать **safe_cast** без **try-catch** блок для обнаружения ошибок программирования во время разработки. Дополнительные сведения см. в разделе [приведение (C + +/ CX)](https://msdn.microsoft.com/library/windows/apps/hh755802.aspx).

### <a name="syntax"></a>Синтаксис

```cpp
[default]:: safe_cast<
type-id
>(
expression
)  
```

### <a name="parameters"></a>Параметры

*Идентификатор типа*  
Целевой тип преобразования *выражение* для. Дескриптор ссылки или типа значения, тип значения или отслеживаемая ссылка на ссылку или тип значения.

*Выражение*  
Выражение, которое оценивается в дескрипторе ссылки или типа значения, типе значения или отслеживаемой ссылке на ссылку или тип значения.

### <a name="remarks"></a>Примечания

**safe_cast** вызывает `InvalidCastException` когда не может преобразовать *выражение* типу, заданному *идентификатор типа*. Для перехвата `InvalidCastException`, укажите [/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md) параметр компилятора и используйте **try/catch** инструкции.

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

**safe_cast** позволяет изменить тип выражения и создать проверяемый код MSIL.

### <a name="syntax"></a>Синтаксис

```cpp
[cli]:: safe_cast<
type-id
>(
expression
)  
```

### <a name="parameters"></a>Параметры

*Идентификатор типа*  
Дескриптор ссылки или типа значения, тип значения или отслеживаемая ссылка на ссылку или тип значения.

*Выражение*  
Выражение, которое оценивается в дескрипторе ссылки или типа значения, типе значения или отслеживаемой ссылке на ссылку или тип значения.

### <a name="remarks"></a>Примечания

Выражение `safe_cast<` *идентификатор типа*`>(`*выражение* `)` преобразует выражение операнда в объект типа type-id.

Компилятор будет принимать [static_cast](../cpp/static-cast-operator.md) в большинстве мест, где он будет принимать **safe_cast**.  Тем не менее **safe_cast** гарантированно создается проверяемый код MSIL, тогда как **static_cast** может создать непроверяемый MSIL.  См. в разделе [чистый и проверяемый код (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) и [Peverify.exe (средство PEVerify)](/dotnet/framework/tools/peverify-exe-peverify-tool) Дополнительные сведения о проверяемом коде.

Как и **static_cast**, **safe_cast** вызывает заданные пользователем преобразования.

Дополнительные сведения о приведении см. в разделе [операторы приведения](../cpp/casting-operators.md).

**safe_cast** не применяется **const_cast** (отвергает **const**).

**safe_cast** находится в пространстве имен cli.  См. в разделе [Platform, default и cli пространств имен](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) Дополнительные сведения.

Дополнительные сведения о **safe_cast**, см. в разделе:

- [Приведение в стиле C с параметром/CLR (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)

- [Практическое руководство. Использование safe_cast в C++/CLI](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

Один пример того, где компилятор не будет принимать **static_cast** , но будет принимать **safe_cast** — приведения между несвязанными типами интерфейса.  С помощью **safe_cast**, компилятор не будет выдавать ошибку преобразования и выполняет проверку во время выполнения, чтобы увидеть, если приведение возможна

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

## <a name="see-also"></a>См. также

[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)