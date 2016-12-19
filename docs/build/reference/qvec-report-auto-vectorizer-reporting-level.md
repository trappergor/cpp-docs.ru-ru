---
title: "/Qvec-report (уровень отчетности автоматического векторизатора) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qvec-report (уровень отчетности автоматического векторизатора)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Включает функцию отчетов компилятора [Автоматический\-Vectorizer](../../parallel/auto-parallelization-and-auto-vectorization.md) и уровень информационных сообщений для вывода во время компиляции.  
  
## Синтаксис  
  
```  
/Qvec-report:{1}{2}  
```  
  
## Заметки  
 **\/Qvec\-report:1**  
 Выводит информационное сообщение для циклов, vectorized.  
  
 **\/Qvec\-report:2**  
 Выводит информационное сообщение для циклов, vectorized и для циклов, не vectorized вместе с кодом причины.  
  
 Дополнительные сведения о кодах причины и сообщениях см. в разделе [Сообщения векторизатора и параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### Задать параметр компилятора \/Qvec\-report в Visual Studio  
  
1.  В области **Обозреватель решений** откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В диалоговом окне **Окна свойств** в поле **C\/C\+\+**, выберите **Командная строка**.  
  
3.  В поле **Дополнительные параметры** введите `/Qvec-report: 1` или `/Qvec-report: 2`.  
  
### Задать параметр компилятора \/Qvec\-report программными средствами  
  
-   Используется в примере кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры \/Q \(низкоуровневые операции\)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Параллельное программирование в машинном коде](http://go.microsoft.com/fwlink/?LinkId=263662)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)