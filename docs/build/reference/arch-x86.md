---
title: -arch (x86) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: 33
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4905634af75f30c5428f8091d736adbe1b8490d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="arch-x86"></a>/arch (x86)
Задает архитектуру для создания кода на платформе x86. См. также [/arch (x64)](../../build/reference/arch-x64.md) и [/arch (ARM)](../../build/reference/arch-arm.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## <a name="arguments"></a>Аргументы  
 **/arch:IA32**  
 Указывает на то, что расширенные инструкции не используются. Также указывает на использование инструкций x87 для вычислений с плавающей запятой.  
  
 **/arch:SSE**  
 Позволяет использовать инструкции SSE.  
  
 **/arch:SSE2**  
 Позволяет использовать инструкции SSE2. Это инструкция по умолчанию на x86 платформы, если не **/arch** параметра.  
  
 **/ arch: AVX**  
 Позволяет использовать инструкции Intel AVX.  
  
 **/ arch: avx2**  
 Позволяет использовать инструкции Intel AVX 2.  
  
## <a name="remarks"></a>Примечания  
 Наборы инструкций SSE и SSE2 имеются в различных процессорах Intel и AMD. Инструкции AVX существуют в процессорах Intel Sandy Bridge и процессорах AMD Bulldozer. Инструкции AVX2 поддерживаются процессорами Intel Haswell и Broadwell, а также процессорами на основе AMD Excavator.  
  
 `_M_IX86_FP`, `__AVX__` И `__AVX2__` макросы указывают, какой, если таковые имеются, **/arch** использовался параметр компилятора. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md). **/Arch: avx2** параметр и `__AVX2__` макрос впервые появились в Visual Studio 2013 с обновлением 2 версии 12.0.34567.1.  
  
 Оптимизатор выбирает, где и как использовать инструкции SSE и SSE2 при **/arch** указано. Наборы инструкций SSE и SSE2 будут использоваться при некоторых скалярных вычислениях с плавающей запятой, если будет обнаружено, что регистры и инструкции SSE или SSE2 дают выигрыш во времени по сравнению со стеком регистров с плавающей запятой x87. В результате код будет использовать для вычислений с плавающей запятой как инструкции x87, так и SSE/SSE2. Кроме того, с **/arch:SSE2**, можно использовать инструкции SSE2 для некоторых операций 64-разрядное целое число.  
  
 В дополнение к наборам инструкций SSE и SSE2 компилятор также использует другие инструкции, имеющиеся в редакциях процессоров, поддерживающих SSE и SSE2. Примером может служить инструкция CMOV, которая впервые появилась в редакции Pentium Pro процессоров Intel.  
  
 Поскольку x86 компилятор создает код, который использует инструкции SSE2 по умолчанию, необходимо указать **/arch:IA32** Чтобы отключить создание инструкций SSE и SSE2 для x86 процессоров.  
  
 **/ arch** только влияет на создание кода для собственных функций. При использовании [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) для компиляции, **/arch** не влияет на создание кода для управляемых функций.  
  
 **/ arch** и [/QIfist](../../build/reference/qifist-suppress-ftol.md) не может использоваться в одной единице компиляции. В частности, если вы не используете `_controlfp` для изменения контрольного слова FP, то код запуска времени выполнения установит 53 бита для поля управления точностью контрольного слова FPU x87. Поэтому каждая операция с типами float и double в выражении выполняется с 53-разрядной мантиссой и 15-разрядной экспонентой. Тем не менее, все операции SSE одиночной точности используют 24-разрядную значащую часть и 8-разрядную экспоненту, а операции SSE2 двойной точности используют 53-разрядную значимую часть и 11-разрядную экспоненту. Дополнительные сведения см. в разделе [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). Подобные отличия возможны в пределах одного дерева выражения, но не в том случае, когда после каждой части выражения стоит пользовательское присваивание. Рассмотрим следующий пример.  
  
```cpp  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 Сравните:  
  
```cpp  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>Установка параметра компилятора для AVX, AVX2, IA32, SSE или SSE2 в Visual Studio  
  
1.  Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **свойства конфигурации**, **C/C++** папки.  
  
3.  Выберите **создания кода** страницу свойств.  
  
4.  Изменить **включить расширенный набор инструкций** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>См. также  
 [/ arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)