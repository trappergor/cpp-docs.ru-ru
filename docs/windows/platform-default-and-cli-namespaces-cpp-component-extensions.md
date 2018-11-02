---
title: Platform, default и cli пространств имен (C + +/ CLI и C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- lang
- cli
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
ms.openlocfilehash: fb7c9135051d790a488775451e1d333ce69d3dda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598012"
---
# <a name="platform-default-and-cli-namespaces--ccli-and-ccx"></a>Platform, default и cli пространств имен (C + +/ CLI и C + +/ CX)

Пространство имен определяет имена языковых элементов таким образом, чтобы они не конфликтовали с именами в других частях исходного кода, которые в противном случае считались бы идентичными. Например, конфликты имен могут не дать компилятору распознать [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md). Пространства имен используются компилятором, но не сохраняются в скомпилированной сборке.

## <a name="all-runtimes"></a>Все среды выполнения

Visual Studio предоставляет пространство имен по умолчанию для проекта, при создании проекта. Можно вручную переименовать пространство имен, несмотря на то что в C + +/ CX имя winmd-файла должно соответствовать имени корневого пространства имен.

## <a name="windows-runtime"></a>Среда выполнения Windows

Дополнительные сведения см. в разделе [пространства имен и видимость типов (C + +/ CX)](https://msdn.microsoft.com/library/windows/apps/hh969551.aspx).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="syntax"></a>Синтаксис

```cpp
using namespace cli;
```

### <a name="remarks"></a>Примечания

C + +/ CLI поддерживает **cli** пространства имен. При компиляции с параметром `/clr`, **с помощью** инструкции в разделе "синтаксис" подразумевается.

Перечисленные ниже возможности языка находятся в **cli** пространство имен:

- [Массивы](../windows/arrays-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)

- [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)

- [safe_cast](../windows/safe-cast-cpp-component-extensions.md)

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода показано, что это можно использовать символ в **cli** пространство имен, что определяемого пользователем символа в коде.  Тем не менее, когда это сделано, необходимо будет явно или неявно определить ссылки на **cli** языковой элемент с тем же именем.

```cpp
// cli_namespace.cpp
// compile with: /clr
using namespace cli;
int main() {
   array<int> ^ MyArray = gcnew array<int>(100);
   int array = 0;

   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062

   // OK
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);
}
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)