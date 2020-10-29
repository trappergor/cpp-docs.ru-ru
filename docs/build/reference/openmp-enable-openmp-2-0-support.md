---
title: /OpenMP (Включение поддержки OpenMP)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: 6bd1ffcd9b21bfe22ed9424ee77edf43100abf6c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921234"
---
# <a name="openmp-enable-openmp-support"></a>/OpenMP (Включение поддержки OpenMP)

Заставляет компилятор обрабатывать [`#pragma omp`](../../preprocessor/omp.md) директивы для поддержки OpenMP.

## <a name="syntax"></a>Синтаксис

::: moniker range=">= msvc-160"

> **/OpenMP** \[ **:**__экспериментально__ ]

::: moniker-end

::: moniker range="<= msvc-150"

> **/OpenMP**

::: moniker-end

## <a name="remarks"></a>Remarks

`#pragma omp` используется для указания [директив](../../parallel/openmp/reference/openmp-directives.md) и [предложений](../../parallel/openmp/reference/openmp-clauses.md). Если параметр **/OpenMP** не указан при компиляции, компилятор игнорирует предложения и директивы OpenMP. Вызовы [функций OpenMP](../../parallel/openmp/reference/openmp-functions.md) обрабатываются компилятором, даже если не указан параметр **/OpenMP** .

::: moniker range=">= msvc-160"

Компилятор C++ в настоящее время поддерживает стандарт OpenMP 2,0. Однако теперь Visual Studio 2019 также предлагает функции SIMD. Чтобы использовать SIMD, Скомпилируйте с помощью параметра **/OpenMP: экспериментальный** . Этот параметр включает как обычные функции OpenMP, так и дополнительные возможности OpenMP SIMD, недоступные при использовании параметра **/OpenMP** .

::: moniker-end

Приложения, компилируемые с помощью параметра **/OpenMP** и **/CLR** , могут выполняться только в одном процессе домена приложения. Несколько доменов приложений не поддерживаются. То есть при запуске конструктора модуля ( `.cctor` ) он определяет, компилируется ли процесс с помощью **/OpenMP** , и если приложение загружается в среду выполнения, не используемую по умолчанию. Дополнительные сведения см. в статьях [AppDomain](../../cpp/appdomain.md), [/CLR (компиляция общеязыковой среды выполнения)](clr-common-language-runtime-compilation.md)и [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md).

При попытке загрузить приложение, скомпилированное с помощью параметра **/OpenMP** и **/CLR** , в домен приложения, отличный от используемого по умолчанию, <xref:System.TypeInitializationException> исключение выдается вне отладчика, а `OpenMPWithMultipleAppdomainsException` в отладчике создается исключение.

Эти исключения также могут возникать в следующих ситуациях.

- Значение, если приложение компилируется с **параметром/CLR** , но не имеет значение **/OpenMP** , и загружается в домен приложения, не являющийся по умолчанию, где процесс включает приложение, скомпилированное с помощью параметра **/OpenMP** .

- При передаче приложения **/CLR** в служебную программу, например [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool), которая загружает целевые сборки в домен приложения, не используемый по умолчанию.

Управление доступом для кода среды CLR не работает в регионах OpenMP. Если атрибут управления доступом для кода CLR применяется за пределами параллельной области, он не будет действовать в параллельной области.

Корпорация Майкрософт не рекомендует создавать приложения **/OpenMP** , разрешающие частично доверенные вызывающие объекты. Не используйте <xref:System.Security.AllowPartiallyTrustedCallersAttribute> или любые атрибуты управления доступом для кода CLR.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните страницу **Свойства**  >  языка **C/C++**  >  **язык** .

1. Измените свойство **поддержки OpenMP** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Пример

В следующем примере показаны некоторые эффекты запуска пула потоков по сравнению с использованием пула потоков после его запуска. При условии, что 64-разрядная, одноядерная, Двухъядерный процессор, пул потоков занимает около 16 мс для запуска. После этого пул потоков будет немного излишним.

При компиляции с параметром **/OpenMP** второй вызов test2 никогда не выполняется дольше, чем при компиляции с помощью **/опенмп-** , так как отсутствует запуск пула потоков. В миллионах итераций версия **/OpenMP** работает быстрее, чем версия **/опенмп-** для второго вызова test2. При 25 итерациях версии **/опенмп-** и **/OpenMP** регистрируются меньше, чем степень гранулярности часов.

Если в приложении имеется только один цикл и он выполняется менее чем на 15 мс (корректирует приблизительную нагрузку на компьютер), то параметр **/OpenMP** может быть не подходящим. Если это более высокое значение, можно использовать параметр **/OpenMP** .

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

## <a name="see-also"></a>См. также статью

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md) \
[Синтаксис Command-Line компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md) \
[OpenMP в MSVC](../../parallel/openmp/openmp-in-visual-cpp.md)
