---
title: -Qpar (автоматический Параллелизатор) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs:
- C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 430bf1ebc79008d97435ecbcb3b15cf19dda5f8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (автоматический параллелизатор)
Включает [автоматического Параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) функции компилятора для автоматически параллелизации циклов в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Qpar  
```  
  
## <a name="remarks"></a>Примечания  
 Когда компилятор автоматически параллелизации циклов в коде, распределяются случайным образом вычисление между несколькими ядрами процессора. Цикл параллелизации подвергается только в том случае, если компилятор определяет, что он является допустимым для этого, и что параллелизации позволяет улучшить производительность.  
  
 `#pragma loop()` Директивы, доступные для оптимизатора параллелизовать определенных циклов. Дополнительные сведения см. в разделе [цикла](../../preprocessor/loop.md).  
  
 Сведения о включении выходных сообщений для автоматического параллелизатора см. в разделе [/qpar-Report (уровень отчетности автоматического Параллелизатора)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).  
  
### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Установка параметра компилятора /Qpar в Visual Studio  
  
1.  В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В **страницы свойств** диалогового **C/C++** выберите **командной строки**.  
  
3.  В **Дополнительные параметры** введите `/Qpar`.  
  
### <a name="to-set-the-qpar-compiler-option-programmatically"></a>Установка параметра компилятора /Qpar программным способом  
  
-   Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)   
 [/ Qpar-report (уровень отчетности автоматического Параллелизатора)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [#pragma loop()](../../preprocessor/loop.md)   
 [Параллельное программирование в машинном коде](http://go.microsoft.com/fwlink/p/?linkid=263662)