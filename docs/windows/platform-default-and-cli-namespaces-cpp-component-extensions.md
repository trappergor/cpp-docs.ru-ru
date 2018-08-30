---
title: Platform, default и cli пространств имен (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- lang
- cli
dev_langs:
- C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 726c9e2653f2914c01d4a45a572614438e12bc8f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194653"
---
# <a name="platform-default-and-cli-namespaces--c-component-extensions"></a>Пространства имен platform, default и cli (расширения компонентов C++)

Пространство имен определяет имена языковых элементов таким образом, чтобы они не конфликтовали с именами в других частях исходного кода, которые в противном случае считались бы идентичными. Например, конфликты имен могут не дать компилятору распознать [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md). Пространства имен используются компилятором, но не сохраняются в скомпилированной сборке.

## <a name="all-runtimes"></a>Все среды выполнения

При создании проекта Visual C++ предоставляет для него пространство имен по умолчанию. Можно вручную переименовать пространство имен, несмотря на то, что в среде выполнения Windows имя winmd-файла должно соответствовать имени корневого пространства имен.

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

[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)