---
title: "-Og (виды глобальной оптимизации) | Документы Microsoft"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
dev_langs:
- C++
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 196e89a958ce49bf5e0087d98d2f40ada210cc87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="og-global-optimizations"></a>/Og (Виды глобальной оптимизации)

Не рекомендуется. Предоставляет локальной и глобальной оптимизации, автоматическое выделение регистров и оптимизацию цикла. Рекомендуется использовать либо [/O1 (минимизировать размер)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) или [/O2 (максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) вместо него.

## <a name="syntax"></a>Синтаксис

> /Og

## <a name="remarks"></a>Примечания

**/Og** является устаревшим. Такая оптимизация обычно включены по умолчанию. Дополнительные сведения об оптимизации см. в разделе [/O1, / O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) или [/Ox (включить наиболее скорость оптимизации)](../../build/reference/ox-full-optimization.md).

Следующие оптимизации можно найти в разделе **/Og**:

- Локальные и глобальные исключение общей части выражения

     При этом виде оптимизации значение общей части выражения вычисляется один раз. В следующем примере если значения `b` и `c` не изменяются для трех выражений, компилятор может назначить вычисление `b + c` во временную переменную и заменить переменную для `b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

     Для локальной оптимизации общей части выражения компилятор проверяет короткие участки кода для общих частей выражения. Для глобальной оптимизации общей части выражения компилятор выполняет все функции для общих частей выражения.

- Автоматическое выделение регистров

     Эта оптимизация позволяет компилятору хранить часто используемые переменные и части выражения в регистрах; `register` ключевого слова пропускается.

- Оптимизация цикла

     Эта оптимизация удаляет инвариантный частей выражения из тела цикла. Оптимальный цикл содержит только выражения, значения которых изменяются через каждого выполнения цикла. В следующем примере выражение `x + y` не изменяется в теле цикла:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

     После оптимизации `x + y` вычисляется один раз, а не при каждом выполнении цикла:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

     Оптимизация цикла гораздо более действует, если компилятор может предположить отсутствие псевдонимов, что набор с [__restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md), или [ограничить](../../cpp/restrict.md).

    > [!NOTE]
    > Можно включить или отключить глобальная оптимизация для функции, функции с помощью `optimize` pragma вместе с `g` параметр.

 Дополнительные сведения см. в разделе [/Oi (Создание встроенных функций)](../../build/reference/oi-generate-intrinsic-functions.md) и [/Ox (включить наиболее скорость оптимизации)](../../build/reference/ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в **Дополнительные параметры** поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)

[Параметры компилятора](../../build/reference/compiler-options.md)

[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)