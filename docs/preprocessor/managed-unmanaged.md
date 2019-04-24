---
title: managed, unmanaged
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
ms.openlocfilehash: 7fa1e3274b85faa9f3f72f4db5bf586ee5d8e274
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022350"
---
# <a name="managed-unmanaged"></a>managed, unmanaged
Позволяет на уровне функций контролировать режим их компиляции: с управляемым или неуправляемым кодом.

## <a name="syntax"></a>Синтаксис

```
#pragma managed
#pragma unmanaged
#pragma managed([push,] on | off)
#pragma managed(pop)
```

## <a name="remarks"></a>Примечания

[/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора содержит элемент управления на уровне модуля для компиляции функции управляемый или неуправляемый.

Неуправляемая функция компилируется для собственной платформы, и среда CLR передает выполнение этой части программы в собственную платформу.

При использовании параметра `/clr` по умолчанию функции компилируются как управляемые.

При применении этих директив pragma выполните следующие действия.

- Добавляйте директиву #pragma перед функцией, а не в теле функции.

- Добавьте директиву pragma после операторов `#include`. Не используйте эти директивы pragma перед операторами `#include`.

Компилятор игнорирует **управляемых** и **неуправляемых** директивы pragma Если `/clr` не используется в компиляцию.

При создании экземпляра шаблонной функции режим ее компиляции (управляемый или неуправляемый код) определяется состоянием этой директивы #pragma в момент определения шаблона.

Дополнительные сведения см. в разделе [Инициализация смешанных сборок](../dotnet/initialization-of-mixed-assemblies.md).

## <a name="example"></a>Пример

```cpp
// pragma_directives_managed_unmanaged.cpp
// compile with: /clr
#include <stdio.h>

// func1 is managed
void func1() {
   System::Console::WriteLine("In managed function.");
}

// #pragma unmanaged
// push managed state on to stack and set unmanaged state
#pragma managed(push, off)

// func2 is unmanaged
void func2() {
   printf("In unmanaged function.\n");
}

// #pragma managed
#pragma managed(pop)

// main is managed
int main() {
   func1();
   func2();
}
```

```Output
In managed function.
In unmanaged function.
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)