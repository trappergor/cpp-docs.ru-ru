---
title: /Zc:inline (удаление COMDAT без ссылки)
ms.date: 09/05/2019
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: f0c0d9a4e5e5f52d239f1a8591006b3d9e369778
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740115"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (удаление COMDAT без ссылки)

Удаляет неиспользуемые функции или данные, являющиеся секциями COMDAT или имеющими только внутреннюю компоновку. Если указан параметр **/Zc: Inline** , компилятор требует, чтобы единицы преобразования, которые используют встроенные данные или встроенные функции, также включали определения для данных или функций.

## <a name="syntax"></a>Синтаксис

> **/Zc: Inline** [ **-** ]

## <a name="remarks"></a>Примечания

Если указан параметр **/Zc: Inline** , компилятор не выдает символьную информацию для функций или данных COMDAT, которые не ссылаются, а также для функций или данных, имеющих только внутреннюю компоновку. Эта оптимизация упрощает часть работы, выполняемую компоновщиком в сборках выпуска, или если указан параметр компоновщика [/OPT: REF](opt-optimizations.md) . Если компилятор выполняет эту оптимизацию, размер файла OBJ может значительно уменьшиться, а скорость работы компоновщика — возрасти. Этот параметр компилятора не включен, если оптимизация отключена ([/OD](od-disable-debug.md)) или если задано значение [/GL (оптимизация всей программы)](gl-whole-program-optimization.md) .

По умолчанию этот параметр отключен ( **/Zc: Inline-** ) в сборках из командной строки. Параметр [/permissive-](permissive-standards-conformance.md) не включает **/Zc: Inline**. В проектах MSBuild этот параметр задается **свойствами** > конфигурации**C++C/**  >  > Language**Удаление нессылающегося кода и свойства данных** , для которых задано значение **Да** . параметры.

Если указан параметр **/Zc: Inline** , компилятор применяет требование c++ 11 к тому, что все объявленные `inline` функции должны иметь определение, доступное в той же записи преобразования, если они используются. Если параметр не указан, компилятор Майкрософт разрешает несогласованный код, который вызывает функции, объявленные `inline` , даже если определение не отображается. Подробнее см. в разделах 3.2 и 7.1.2 стандарта C++11. Этот параметр компилятора появился в Visual Studio 2013 с обновлением 2.

Чтобы использовать параметр **/Zc: Inline** , обновите код, не соответствующий требованиям.

В этом примере показано, как несоответствующее использование объявления встроенной функции без определения по-прежнему компилируется и ссылки при использовании параметра **/Zc: Inline-** Option по умолчанию:

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

Если параметр **/Zc: Inline** включен, то тот же код вызывает ошибку [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) , так как компилятор не выдает текст невстроенного кода для `Example::inline_call` в файле example. obj. Из-за этого неподставляемый вызов в `main` ссылается на неопределенный внешний символ.

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

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **конфигурации** > **C/C++**  > **Language** .

1. Измените **нессылающийся код и свойство данных** , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)<br/>
