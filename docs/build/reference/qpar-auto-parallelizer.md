---
title: /Qpar (автоматический параллелизатор)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: c1ddea73c5aa8d3e7e70b45834cb04154bf3b4bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319230"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (автоматический параллелизатор)

Позволяет [автоматического Параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) функция компилятора для автоматически параллельного выполнения циклов в коде.

## <a name="syntax"></a>Синтаксис

```
/Qpar
```

## <a name="remarks"></a>Примечания

Когда компилятор автоматически параллелизуются циклы в коде, он распределяет вычисления между несколькими ядрами процессора. Только в том случае, если компилятор определяет, что можно сделать и параллелизации, что позволяет улучшить производительность параллелизации цикла.

`#pragma loop()` Директивы, доступные для помогают оптимизатору параллельного выполнения определенных циклов. Дополнительные сведения см. в разделе [цикла](../../preprocessor/loop.md).

Сведения о способах включения выходных сообщений для автоматическим параллелизатором, см. в разделе [/qpar-Report (уровень отчетности автоматического Параллелизатора)](qpar-report-auto-parallelizer-reporting-level.md).

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Установка параметра компилятора /Qpar в Visual Studio

1. В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.

1. В **страницы свойств** диалогового **C/C++** выберите **командной строки**.

1. В **Дополнительные параметры** введите `/Qpar`.

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>Установка параметра компилятора /Qpar программным способом

- Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](q-options-low-level-operations.md)<br/>
[/Qpar/report (уровень отчетности автоматического параллелизатора)](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[#pragma loop()](../../preprocessor/loop.md)<br/>
[Параллельное программирование в машинном коде](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
