---
title: -openmp (Включение поддержки OpenMP 2.0) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
dev_langs:
- C++
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6ba594249ff2a6551519d4254ff526cbd03fa97
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704110"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (включение поддержки OpenMP 2.0)

Указывает компилятору обрабатывать `#pragma` [omp](../../preprocessor/omp.md).

## <a name="syntax"></a>Синтаксис

```
/openmp
```

## <a name="remarks"></a>Примечания

`#pragma omp` используется для указания [директивы](../../parallel/openmp/reference/openmp-directives.md) и [предложения](../../parallel/openmp/reference/openmp-clauses.md). Если **/OpenMP** не указан при компиляции, компилятор игнорирует предложения и директивы OpenMP. [OpenMP-функция](../../parallel/openmp/reference/openmp-functions.md) обработки вызовов, даже если компилятор **/OpenMP** не указан.

Приложения, скомпилированные с **/OpenMP** и **/CLR** может выполняться только в процессе домена одного приложения; несколько доменов приложения, не поддерживаются. То есть при выполнении конструктора модуля (.cctor), она обнаружит, процесс компилируется с **/OpenMP** и если приложение загружается в среду выполнения не по умолчанию. Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md), [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md), и [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md).

При попытке загрузить приложение, скомпилированное с **/OpenMP** и **/CLR** в домен приложения не по умолчанию, <xref:System.TypeInitializationException> исключение вне отладчика и OpenMPWithMultipleAppdomainsException исключение в отладчике.

Кроме того, эти исключения могут возникать в следующих ситуациях:

- Если приложение компилируется с **/CLR**, но не с **/OpenMP**, загружается в домен приложения не по умолчанию, но где процесс включает в себя приложение, скомпилированное с **/ OpenMP**.

- При передаче вашего **/CLR** приложения к служебной программе, например regasm.exe ([Regasm.exe (средство регистрации сборок)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), который загружает ее целевой сборки в домен приложения не по умолчанию.

Разграничение доступа кода среды CLR не работает в области OpenMP. Если применить атрибут безопасности доступа кода CLR вне параллельной области, он не будет действовать в параллельной области.

Корпорация Майкрософт рекомендует не писать **/OpenMP** приложений, которые позволяет частично доверяемого кода, с помощью <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, или любые атрибуты безопасности доступа кода среды CLR.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **C/C++** узла.

1. Выберите **языка** страницу свойств.

1. Изменить **поддержка OpenMP** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Пример

Приведенный ниже показаны некоторые последствия запуска пула потоков по сравнению с использованием threadpool, после запуска. При условии, что x x64 одном ядре, пула потоков занимает около 16ms запуска. После этого не менее, это небольшая цена для пула потоков.

При выполнении компиляции с **/OpenMP**, второй вызов test2 никогда не будет выполняться дольше, чем при компиляции с параметром **/openmp-**, поскольку отсутствует запуск пула потоков. После миллиона итераций **/OpenMP** версия работает быстрее, чем **/openmp-** версии для второго вызова test2 и при 25 итерациях **/openmp-** и **/OpenMP** версий register меньше, чем гранулярность часов.

Таким образом, если у вас есть только один цикл в приложении, и он выполняется менее 15 мс (с учетом приблизительных издержек на вашем компьютере), **/OpenMP** может не подойти, но если это что-либо еще, вы можете рассмотреть возможность использования **/OpenMP**.

```
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

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)