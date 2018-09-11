---
title: -Qpar (автоматический Параллелизатор) | Документация Майкрософт
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
ms.openlocfilehash: 24c3501422a0bfbaba8aea0e45c102f63948b7db
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684509"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (автоматический параллелизатор)
Позволяет [автоматического Параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) функция компилятора для автоматически параллельного выполнения циклов в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Qpar  
```  
  
## <a name="remarks"></a>Примечания  
 Когда компилятор автоматически параллелизуются циклы в коде, он распределяет вычисления между несколькими ядрами процессора. Только в том случае, если компилятор определяет, что можно сделать и параллелизации, что позволяет улучшить производительность параллелизации цикла.  
  
 `#pragma loop()` Директивы, доступные для помогают оптимизатору параллельного выполнения определенных циклов. Дополнительные сведения см. в разделе [цикла](../../preprocessor/loop.md).  
  
 Сведения о способах включения выходных сообщений для автоматическим параллелизатором, см. в разделе [/qpar-Report (уровень отчетности автоматического Параллелизатора)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).  
  
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
 [Параллельное программирование в машинном коде](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)