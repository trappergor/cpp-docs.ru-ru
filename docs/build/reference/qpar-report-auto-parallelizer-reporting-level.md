---
title: "-Qpar-report (уровень отчетности автоматического Параллелизатора) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70ae055d69341cc773b8b40ed1111b65ba5683cf
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (уровень отчетности автоматического параллелизатора)
Включает функцию создания отчетов компилятора [автоматического Параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) и указывает уровень информационных сообщений, выводимых при компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>Примечания  
 **/ Qpar-report: 1**  
 Выводит информационное сообщение для распараллеленных циклов.  
  
 **/ Qpar-report: 2**  
 Выводит информационное сообщение для распараллеленных циклов, а также для тех циклов, которые не были распараллелены, с указанием кода причины.  
  
 Сообщения выводятся в stdout. Если информационные сообщения отсутствуют, то либо код не содержит циклов, либо уровень отчетности не настроен для передачи отчетов о циклах, которые не удалось распараллелить. Дополнительные сведения о кодах причин и сообщениях см. в разделе [сообщения Векторизатора и Параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Настройка параметра компилятора /Qpar-report в Visual Studio  
  
1.  В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В **страницы свойств** диалогового **C/C++**выберите **командной строки**.  
  
3.  В **Дополнительные параметры** введите `/Qpar-report:1` или `/Qpar-report:2`.  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>Настройка параметра компилятора /Qpar-report программным способом  
  
-   Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Параллельное программирование в машинном коде](http://go.microsoft.com/fwlink/p/?linkid=263662)