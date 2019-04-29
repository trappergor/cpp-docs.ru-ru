---
title: / OpenMP (Включение поддержки OpenMP)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: caa06d89c590abd2b3a74a5a6b118d6ba4acd910
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320218"
---
# <a name="openmp-enable-openmp-support"></a>/ OpenMP (Включение поддержки OpenMP)

Указывает компилятору обрабатывать [ `#pragma omp` ](../../preprocessor/omp.md) директивы OpenMP, входящих в несущее множество.

## <a name="syntax"></a>Синтаксис

::: moniker range=">= vs-2019"

> **/ openmp**\[**:**__экспериментальный__]

::: moniker-end

::: moniker range="<= vs-2017"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>Примечания

`#pragma omp` используется для указания [директивы](../../parallel/openmp/reference/openmp-directives.md) и [предложения](../../parallel/openmp/reference/openmp-clauses.md). Если **/OpenMP** не указан, компилятор игнорирует предложения и директивы OpenMP. [OpenMP-функция](../../parallel/openmp/reference/openmp-functions.md) обработки вызовов, даже если компилятор **/OpenMP** не указан.

::: moniker range=">= vs-2019"

C++ Компилятора в настоящее время поддерживает стандарт OpenMP 2.0. Тем не менее 2019 г. Visual Studio теперь также предлагает функциональные возможности SIMD. Чтобы использовать SIMD, компиляция с помощью **/OpenMP: экспериментальный** параметр. Этот параметр поддерживает обычные возможности OpenMP, а дополнительные OpenMP SIMD недоступно при использовании **/OpenMP** переключения.

::: moniker-end

Приложения, скомпилированные с помощью обоих **/OpenMP** и **/CLR** может выполняться только в процессе домена одного приложения. Несколько доменов приложений, не поддерживаются. То есть, когда конструктор модуля (`.cctor`) — запустить, обнаруживает, если процесс компилируется с помощью **/OpenMP**, и если приложение загружается в среду выполнения не по умолчанию. Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md), [/CLR (компиляция CLR)](clr-common-language-runtime-compilation.md), и [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md).

При попытке загрузить приложение скомпилировано с использованием обоих **/OpenMP** и **/CLR** в домен приложения не по умолчанию, <xref:System.TypeInitializationException> вне отладчика, исключения и `OpenMPWithMultipleAppdomainsException` исключение возникает в отладчике.

Кроме того, эти исключения могут возникать в следующих ситуациях:

- Если приложение компилируется с помощью **/CLR** , но не **/OpenMP**и загружается в домен приложения не по умолчанию, где процесс включает в себя приложение скомпилировано с использованием   **/OpenMP**.

- При передаче вашего **/CLR** приложения со служебной программой, например [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool), который загружает ее целевой сборки в домен приложения не по умолчанию.

Разграничение доступа кода среды CLR не работает в области OpenMP. Если применить атрибут безопасности доступа кода CLR вне параллельной области, он не будет действовать в параллельной области.

Корпорация Microsoft не рекомендует создавать **/OpenMP** приложения, разрешить частично доверенные вызывающие объекты. Не используйте <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, или любые атрибуты безопасности доступа кода среды CLR.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Разверните **свойства конфигурации** > **C /C++** > **языка** страницу свойств.

1. Изменить **поддержка OpenMP** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Пример

Приведенный ниже показаны некоторые последствия запуска пула потоков и используя пул потоков, после ее запуска. При условии, что x x64 одно ядро, два процессора, пул потоков занимает около 16 мс для запуска. После этого немного дополнительная плата для пула потоков.

При компиляции с помощью **/OpenMP**, второй вызов test2 никогда не будет выполняться дольше, чем при компиляции с помощью **/openmp-**, поскольку отсутствует без запуска пула потоков. После миллиона итераций **/OpenMP** версия работает быстрее, чем **/openmp-** версии для второй вызов test2. В 25 итераций оба **/openmp-** и **/OpenMP** версий register меньше, чем гранулярность часов.

Если у вас есть только один цикл в приложении, и он выполняется менее 15 мс (с учетом приблизительных издержек на вашем компьютере), **/OpenMP** может не подойти. Если выше, вы можете рассмотреть возможность использования **/OpenMP**.

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md) \
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md) \
[OpenMP в MSVC](../../parallel/openmp/openmp-in-visual-cpp.md)
