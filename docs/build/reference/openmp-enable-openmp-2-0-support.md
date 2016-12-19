---
title: "/openmp (включение поддержки OpenMP 2.0) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/openmp"
  - "VC.Project.VCCLCompilerTool.OpenMP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/openmp - параметр компилятора [C++]"
  - "-openmp - параметр компилятора [C++]"
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /openmp (включение поддержки OpenMP 2.0)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инициирует обработку компилятором прагма\-директивы `#pragma` [omp](../../preprocessor/omp.md).  
  
## Синтаксис  
  
```  
/openmp  
```  
  
## Заметки  
 Директива `#pragma omp` используется для задания директив [Directives](../../parallel/openmp/reference/openmp-directives.md) и предложений [Clauses](../../parallel/openmp/reference/openmp-clauses.md).  Если параметр **\/openmp** не указан, компилятор игнорирует предложения и директивы OpenMP.  Вызовы [функций OpenMP](../../parallel/openmp/reference/openmp-functions.md) обрабатываются компилятором даже в том случае, если параметр **\/openmp** не указан.  
  
 Приложение, скомпилированное с параметром **\/openmp** и использующее библиотеки [Libraries](../../parallel/openmp/reference/openmp-libraries.md), может выполняться только в операционной системе Windows 2000 и более поздних версиях.  
  
 Приложения, скомпилированные с параметрами **\/openmp** и **\/clr**, могут выполняться только в процессе с одиночным доменом приложения; множественные домены приложений не поддерживаются.  Это означает, что при выполнении конструктор модуля \(.cctor\) будет определять, использовался ли при компиляции процесса параметра **\/openmp**, и не загружается ли приложение в среду выполнения, не заданную по умолчанию.  Дополнительные сведения см. в разделах [appdomain](../Topic/appdomain.md), [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) и [Инициализация смешанных сборок](../Topic/Initialization%20of%20Mixed%20Assemblies.md).  
  
 При попытке загрузить приложение, скомпилированное с параметрами **\/openmp** и **\/clr**, в домен приложения, не заданный по умолчанию, вне отладчика возникнет исключение <xref:System.TypeInitializationException>, а в отладчике возникнет исключение OpenMPWithMultipleAppdomainsException.  
  
 Эти исключения также могут возникать в следующих ситуациях:  
  
-   Если приложение, скомпилированное с параметром **\/clr**, но без параметра **\/openmp**, загружается в домен приложения, не заданный по умолчанию, но в котором процесс включает приложение, скомпилированное с параметром **\/openmp**.  
  
-   Если приложение **\/clr** передается служебной программе, например regasm.exe \(см. раздел [Regasm.exe \(Assembly Registration Tool\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)\), которая загружает свои целевые сборки в домен приложения, не заданный по умолчанию.  
  
 Управление доступом для кода среды CLR не работает в областях OpenMP.  Если атрибут управления доступом для кода среды CLR применяется вне параллельной области, то он не будет действовать в параллельной области.  
  
 Корпорация Майкрософт не рекомендует создавать приложения **\/openmp**, допускающие вызовы с частичным доверием с помощью атрибута <xref:System.Security.AllowPartiallyTrustedCallersAttribute> или любых атрибутов управления доступом для кода среды CLR.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **C\/C\+\+**.  
  
4.  Выберите страницу свойств **Язык**.  
  
5.  Измените значение свойства **Поддержка OpenMP**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.  
  
## Пример  
 В следующем примере показаны результаты запуска пула потоков по сравнению с использованием пула потоков после запуска.  Одноядерному двухпроцессорному компьютеру с архитектурой x64 потребуется около 16 мс для запуска пула потоков.  Тем не менее, это небольшая цена для пула потоков.  
  
 При компиляции с параметром **\/openmp** второй вызов test2 никогда не будет работать дольше, чем если бы компиляция была выполнена с параметром **\/openmp\-**, поскольку отсутствует запуск пула потоков.  После миллиона итераций версия с параметром **\/openmp** для второго вызова test2 будет быстрее, чем версия с параметром **\/openmp\-**, а при 25 итерациях разница между версиями **\/openmp\-** и **\/openmp** не будет превышать единицу разрешения часов.  
  
 Таким образом, если в приложении имеется только один цикл, и он выполняется быстрее, чем за 15 мс \(с учетом приблизительных издержек компьютера\), то параметр **\/openmp** может не подойти, но если кроме цикла имеется что\-либо еще, то имеет смысл подумать об использовании параметра **\/openmp**.  
  
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
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)