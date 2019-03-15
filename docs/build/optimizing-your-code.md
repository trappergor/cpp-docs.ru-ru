---
title: Оптимизация кода
ms.date: 12/10/2018
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: ae60070959c683a6365992e7b6cc510fd4111b36
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57828103"
---
# <a name="optimizing-your-code"></a>Оптимизация кода

Оптимизировав исполняемый файл, можно добиться баланса между высокой скоростью выполнения и небольшим размером кода. В этом разделе рассматриваются некоторые из механизмов, предоставляемых Visual C++ для оптимизации кода.

## <a name="language-features"></a>Возможности языка

Ниже описаны некоторые средства оптимизации на языке C/C++.

[Директивы pragma и ключевые слова оптимизации](optimization-pragmas-and-keywords.md)<br/>
Список ключевых слов и директивы pragma, что в коде можно использовать для повышения производительности.

[Параметры компилятора, упорядоченные по категориям](reference/compiler-options-listed-by-category.md)<br/>
Список **/O** параметры компилятора, которые влияют на скорость выполнения или кода размер.

[Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md)<br/>
Ссылки rvalue поддерживают реализацию *семантику перемещения*. Если перемещение семантику, используемые для реализации библиотеки шаблонов, производительность приложения, использующие эти шаблоны может значительно повысить.

### <a name="the-optimize-pragma"></a>Директива pragma optimize

Если раздел оптимизированного кода возникают ошибки или замедление работы, можно использовать [оптимизировать](../preprocessor/optimize.md) директивы pragma, для отключения оптимизации для этого раздела.

Поместите его между двумя директив pragma, как показано ниже:

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>Примеры программирования

Вы можете заметить дополнительных предупреждений, при компиляции кода с оптимизацией. Такое поведение считается нормальным, так как некоторые предупреждения относятся только к оптимизированного кода. Многие оптимизации этих проблем можно избежать, если некоторые моменты.

Парадоксально, но оптимизация быстродействия программы может вызвать код будет работать медленнее. Это, так как некоторые процессы оптимизации быстродействия увеличить размер кода. К примеру, встраивание функций устраняет затраты на вызовы функций. Тем не менее встраивание слишком большого объема кода программы может увеличиться настолько большим, что номер страницы виртуальной памяти увеличивается при сбоях. Таким образом увеличение быстродействия вследствие отказа от вызовов функции могут быть потеряны в памяти подкачки.

В следующих разделах рассматриваются рекомендуемые методы программирования.

[Рекомендации по оптимизации срочного кода](tips-for-improving-time-critical-code.md)<br/>
Более эффективное кодирование методики может привести к повышению производительности. В этом разделе описываются методы, которые помогут вам убедитесь в том, что срочные части кода выполняются удовлетворительно написания кода.

[Рекомендации по оптимизации](optimization-best-practices.md)<br/>
Предоставляет общие рекомендации по оптимизации приложения.

## <a name="debugging-optimized-code"></a>Отладка оптимизированного кода

Оптимизация может изменить код, созданный компилятором, поэтому рекомендуется отладки приложения и измерения его производительности и затем оптимизации кода.

В следующих разделах приводятся сведения об отладке версии сборки.

- [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)

- [Практическое руководство. Отладка оптимизированного кода](/visualstudio/debugger/how-to-debug-optimized-code)

- [Почему может уменьшиться точность чисел с плавающей запятой](why-floating-point-numbers-may-lose-precision.md)


Ниже представлены сведения об оптимизации создания, загрузки и выполнения кода.

- [Улучшение производительности компилятора](improving-compiler-throughput.md)

- [При использовании имен функций без скобок () код не создается](using-function-name-without-parens-produces-no-code.md)

- [Оптимизация встроенного кода на языке ассемблера](../assembler/inline/optimizing-inline-assembly.md)

- [Настройка оптимизации компилятора для проекта ATL](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Способы оптимизации следует использовать для повышения производительности клиентского приложения при загрузке?](../build/dll-frequently-asked-questions.md#mfc_optimization)


## <a name="in-this-section"></a>В данном разделе

[Директивы pragma и ключевые слова оптимизации](optimization-pragmas-and-keywords.md)<br/>
[Улучшение производительности компилятора](improving-compiler-throughput.md)<br/>
[Почему может уменьшиться точность чисел с плавающей запятой](why-floating-point-numbers-may-lose-precision.md)<br/>
[IEEE-представление с плавающей запятой](ieee-floating-point-representation.md)<br/>
[Рекомендации по оптимизации срочного кода](tips-for-improving-time-critical-code.md)<br/>
[При использовании имен функций без скобок () код не создается](using-function-name-without-parens-produces-no-code.md)<br/>
[Рекомендации по оптимизации](optimization-best-practices.md)<br/>
[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[Переменные среды для профильной оптимизации](environment-variables-for-profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgomgr](pgomgr.md)<br/>
[pgosweep](pgosweep.md)<br/>
[Практическое руководство. Слияние нескольких профилей для профильной оптимизации](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
[Надстройка вероятностного оптимизатора Visual Studio 2013 в разделе производительности и диагностики](profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)<br/>

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](reference/c-cpp-building-reference.md)
