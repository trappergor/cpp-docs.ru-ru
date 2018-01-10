---
title: "-CGTHREADS (потоки компилятора) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 542e35ecbb5e56ae0d13861b9885936f3b47c9da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (потоки компилятора)
Задает число потоков cl.exe, используемых для оптимизации и создания кода, если задано создание кода во время компоновки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/CGTHREADS:[1-8]  
```  
  
## <a name="arguments"></a>Аргументы  
 number  
 Максимальное число потоков, используемых cl.exe, — в диапазоне от 1 до 8.  
  
## <a name="remarks"></a>Примечания  
 **/Cgthreads** параметр определяет максимальное количество потоков, используемых программой cl.exe параллельно на этапах оптимизации и создания кода при связи во время компиляции, при создании кода ([/LTCG](../../build/reference/ltcg-link-time-code-generation.md)) — указано. По умолчанию cl.exe использует четыре потока, как если бы **/CGTHREADS:4** были указаны. Если доступно больше ядер процессора, увеличение значения `number` может ускорить сборку.  
  
 Для сборки можно указать несколько уровней параллелизма. Параметр msbuild.exe **/maxcpucount** указывает число процессов MSBuild, которые могут выполняться параллельно. [/MP (построить с несколькими процессами)](../../build/reference/mp-build-with-multiple-processes.md) флаг компилятора указывает число процессов cl.exe, которые одновременно компиляции исходных файлов. [/Cgthreads](../../build/reference/cgthreads-code-generation-threads.md) параметр компилятора задает число потоков, используемых каждым процессом cl.exe. Так как число потоков, одновременно выполняемых процессором, не может превышать число ядер процессора, указывать более высокие значения для всех этих параметров бессмысленно. Более того, это может иметь обратный эффект. Дополнительные сведения о построении проектов в параллельном режиме см. в разделе [параллельное построение нескольких проектов](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **свойства конфигурации**, **компоновщика** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив **/cgthreads:**`number`, где `number` — значение от 1 до 8, а затем выберите **ОК**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)