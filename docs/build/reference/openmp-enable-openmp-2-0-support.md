---
title: -openmp (Включение поддержки OpenMP 2.0) | Документы Microsoft
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
ms.openlocfilehash: fe64011f48255a18aa8f8ccab7571533540a598a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378734"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (включение поддержки OpenMP 2.0)
Указывает компилятору на необходимость обработки `#pragma` [omp](../../preprocessor/omp.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/openmp  
```  
  
## <a name="remarks"></a>Примечания  
 `#pragma omp` используется для указания [директивы](../../parallel/openmp/reference/openmp-directives.md) и [предложения](../../parallel/openmp/reference/openmp-clauses.md). Если **/OpenMP** не указан во время компиляции, компилятор игнорирует предложения и директивы OpenMP. [OpenMP-функция](../../parallel/openmp/reference/openmp-functions.md) даже если компилятор обрабатывает вызовы **/OpenMP** не указан.  
  
 Приложения, скомпилированные с **/OpenMP** и **/CLR** могут выполняться только в процессе домена одним приложением, не поддерживаются несколько доменов приложений. То есть, при выполнении конструктора модуля (.cctor) будет определять, процесс компилируется с **/OpenMP** и если приложение загружается в среде выполнения не по умолчанию. Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md), [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md), и [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md).  
  
 При попытке загрузить приложение, скомпилированное с **/OpenMP** и **/CLR** в домен приложения не по умолчанию, <xref:System.TypeInitializationException> исключение вне отладчика и OpenMPWithMultipleAppdomainsException исключение в отладчике.  
  
 Эти исключения, также могут возникать в следующих ситуациях:  
  
-   Если приложение компилируется с **/CLR**, но не с **/OpenMP**, загружается в домен приложения не по умолчанию, но когда процесс включает в себя приложение, скомпилированное с **/ OpenMP**.  
  
-   Если передать вашей **/CLR** приложения со служебной программой, например regasm.exe ([Regasm.exe (средство регистрации сборок)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), который загружает его целевые сборки в домен приложения не по умолчанию.  
  
 Управление доступом для кода среды CLR не работает в областях OpenMP. Если применить атрибут безопасности доступа кода CLR вне параллельной области, он не будет действовать в параллельной области.  
  
 Корпорация Майкрософт не рекомендует не писать **/OpenMP** приложений, которые позволяет частично доверенным вызывающим объектам, с помощью <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, или любые атрибуты безопасности доступа кода среды CLR.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **C/C++** узла.  
  
4.  Выберите **языка** страницу свойств.  
  
5.  Изменить **поддержка OpenMP** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример некоторых эффектов запуска пула потоков по сравнению с использованием пула потоков после запуска. При условии, что x64 одного ядра пула потоков занимает около мегабайтного запуска. После этого не менее, это очень низкие затраты для пула потоков.  
  
 При компиляции с **/OpenMP**, второй вызов test2 никогда не выполняется дольше, чем при компиляции с **/openmp-**, поскольку отсутствует запуск пула потоков. После миллиона итераций **/OpenMP** версия выполняется быстрее, чем **/openmp-** версию для второго вызова test2 и при 25 итерациях **/openmp-** и **/OpenMP** регистра версии меньше, чем гранулярность часов.  
  
 Таким образом, если имеется только один цикл в приложении, и он выполняется не более 15 мс (с учетом приблизительных издержек компьютера), **/OpenMP** может не подойти, но если что-либо еще, вы можете рассмотреть возможность использования **/OpenMP**.  
  
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
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)