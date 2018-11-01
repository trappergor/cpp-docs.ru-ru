---
title: /Zc:inline (удаление COMDAT без ссылки)
ms.date: 03/01/2018
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: 6855773c6ec807a7488fa5604ddee7fd43983135
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441240"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (удаление COMDAT без ссылки)

Удаляет неиспользуемые функции или данные, являющиеся секциями COMDAT или имеющими только внутреннюю компоновку. Когда **/Zc: inline** указан, компилятор требует записей преобразования, которые используются встраиваемые данные или встроенные функции необходимо также включить определения для данных или функций.

## <a name="syntax"></a>Синтаксис

> **/ Zc: inline**[**-**]

## <a name="remarks"></a>Примечания

Когда **/Zc: inline** указан, компилятор не выдает символьную информацию для неиспользуемые функции COMDAT или данные, или для функции или данные, которые имеют только внутреннюю компоновку. Эта оптимизация упрощает часть работы, выполняемой компоновщиком в сборках выпуска или если параметр компоновщика [предотвратят](../../build/reference/opt-optimizations.md) указан. Если компилятор выполняет эту оптимизацию, размер файла OBJ может значительно уменьшиться, а скорость работы компоновщика — возрасти. Этот параметр компилятора не включена, если отключены оптимизации ([/Od](../../build/reference/od-disable-debug.md)) или когда [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md) указан.

По умолчанию этот параметр отключен (**/Zc:inline-**). [/ Permissive-](permissive-standards-conformance.md) параметр не позволяет включить **/Zc: inline**.

Если **/Zc: inline** указан, компилятор применяет C ++ 11 требования, все функции, объявленные `inline` должен иметь определение в той же записи преобразования, если они используются. Если параметр не указан, компилятор Microsoft позволяет не соответствующего стандарту кода, который вызывает функции, объявленные `inline` даже, если определение недоступно. Подробнее см. в разделах 3.2 и 7.1.2 стандарта C++11. Этот параметр компилятора появился в Visual Studio 2013 с обновлением 2.

Чтобы использовать **/Zc: inline** параметр несовместимые кода обновления.

В этом примере показано, как несовместимые использование объявления встраиваемой функции без определения по-прежнему компилируется и ссылки, когда значение по умолчанию **/Zc:inline-** используется параметр:

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n");
}

void Example::normal_call() {
   printf("normal_call was called.\n");
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

При **/Zc: inline** включена, этот же код вызывает [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) ошибка, так как компилятор не выдает неподставляемый код тела `Example::inline_call` в файле example.obj. Из-за этого неподставляемый вызов в `main` ссылается на неопределенный внешний символ.

Чтобы устранить эту ошибку, можно удалить ключевое слово `inline` из объявления `Example::inline_call`, перенести определение `Example::inline_call` в файл заголовка или перенести реализацию `Example` в файл main.cpp. В следующем примере определение переносится в файл заголовка, где оно доступно любому вызывающему объекту, включающему заголовок.

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n");
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n");
   inline_call();
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **языка** страницу свойств.

1. Изменить **удалить неиспользуемые кода и данных** свойство, а затем выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
