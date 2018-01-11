---
title: "-Qvec-report (уровень отчетности автоматического Векторизатора) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43c9a182046ff148621151107a98932cc39835f2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (уровень отчетности автоматического векторизатора)
Включает функцию создания отчетов компилятора [автоматический Векторизатор](../../parallel/auto-parallelization-and-auto-vectorization.md) и указывает уровень информационных сообщений, выводимых при компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Qvec-report:{1}{2}  
```  
  
## <a name="remarks"></a>Примечания  
 **/ Qvec-report: 1**  
 Выводит информационное сообщение для циклов, которые являются векторизован.  
  
 **/ Qvec-report: 2**  
 Выводит информационное сообщение для циклов, которые являются векторизован и циклы, которые не являются векторизован, с указанием кода причины.  
  
 Сведения о кодах причин и сообщениях см. в разделе [сообщения Векторизатора и Параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Установка параметра компилятора /Qvec-report в Visual Studio  
  
1.  В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В **страницы свойств** диалогового **C/C++**выберите **командной строки**.  
  
3.  В **Дополнительные параметры** введите `/Qvec-report:1` или `/Qvec-report:2`.  
  
### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>Установка параметра компилятора /Qvec-report программным способом  
  
-   Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Параллельное программирование в машинном коде](http://go.microsoft.com/fwlink/p/?linkid=263662)