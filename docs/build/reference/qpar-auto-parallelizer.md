---
title: /Qpar (автоматический параллелизатор)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: 18aaa1dc678ca2c73f9fad6c016aa40cfa95982b
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373805"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (автоматический параллелизатор)

Включает функцию [автоматического параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) в компиляторе для автоматической параллелизации циклов в коде.

## <a name="syntax"></a>Синтаксис

```
/Qpar
```

## <a name="remarks"></a>Remarks

Когда компилятор автоматически параллелизуются циклы в коде, он распределяет вычисления по нескольким процессорным ядрам. Цикл параллельно выполняется, только если компилятор определяет, что это допустимо, и что параллелизм повысит производительность.

`#pragma loop()`Доступны директивы, помогающие оптимизатору параллельно выполнять циклы. Дополнительные сведения см. в разделе [Loop](../../preprocessor/loop.md).

Сведения о том, как включить выходные сообщения для Auto-параллелизатора, см. в разделе [/Qpar-report (уровень отчетов Auto-параллелизатора)](qpar-report-auto-parallelizer-reporting-level.md).

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Установка параметра компилятора/Qpar в Visual Studio

1. В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.

1. В диалоговом окне **страницы свойств** в разделе **C/C++** выберите пункт **Командная строка**.

1. В поле **Дополнительные параметры** введите `/Qpar` .

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>Установка параметра компилятора/Qpar программным способом

- Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры/q (низкоуровневые операции)](q-options-low-level-operations.md)<br/>
[/Qpar-report (автоматический уровень отчетов Параллелизатора)](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)<br/>
[цикл #pragma ()](../../preprocessor/loop.md)<br/>
[Вектор машинного кода в Visual Studio](https://docs.microsoft.com/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
