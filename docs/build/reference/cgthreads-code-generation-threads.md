---
title: -cgthreads (потоки создания кода) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /cgthreads
dev_langs:
- C++
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32c88fe00958a0fc767d8a316bfe4edab7b4fb0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (потоки создания кода)
Задает число потоков cl.exe, используемых для оптимизации и создания кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/cgthreads[1-8]  
```  
  
## <a name="arguments"></a>Аргументы  
 number  
 Максимальное число потоков, используемых cl.exe, — в диапазоне от 1 до 8.  
  
## <a name="remarks"></a>Примечания  
 **/Cgthreads** определяет максимальное число потоков cl.exe, используемых программой параллельно для оптимизации и код создания этапа компиляции. Обратите внимание, что может быть пробела между **/cgthreads** и `number` аргумент. По умолчанию cl.exe использует четыре потока, как если бы **/cgthreads4** были указаны. Если доступно больше ядер процессора, увеличение значения `number` может ускорить сборку. Этот параметр особенно полезен, когда он объединяется с [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).  
  
 Для сборки можно указать несколько уровней параллелизма. Параметр msbuild.exe **/maxcpucount** указывает число процессов MSBuild, которые могут выполняться параллельно. [/MP (построить с несколькими процессами)](../../build/reference/mp-build-with-multiple-processes.md) флаг компилятора указывает число процессов cl.exe, которые одновременно компиляции исходных файлов. **/Cgthreads** параметр задает число потоков, используемых каждым процессом cl.exe. Так как число потоков, одновременно выполняемых процессором, не может превышать число ядер процессора, указывать более высокие значения для всех этих параметров бессмысленно. Более того, это может иметь обратный эффект. Дополнительные сведения о построении проектов в параллельном режиме см. в разделе [параллельное построение нескольких проектов](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **свойства конфигурации**, **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив **/cgthreads**`N`, где `N` — значение от 1 до 8, а затем выберите **ОК**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)