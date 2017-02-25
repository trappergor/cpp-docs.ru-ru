---
title: "/Qpar-report (уровень отчетности автоматического параллелизатора) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Qpar-report (уровень отчетности автоматического параллелизатора)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Включает функцию создания отчетов [автоматического параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) компилятора и указывает уровень информационных сообщений, выводимых при компиляции.  
  
## Синтаксис  
  
```  
/Qpar-report:{1}{2}  
```  
  
## Заметки  
 **\/Qpar\-report:1**  
 Выводит информационное сообщение для распараллеленных циклов.  
  
 **\/Qpar\-report:2**  
 Выводит информационное сообщение для распараллеленных циклов, а также для тех циклов, которые не были распараллелены, с указанием кода причины.  
  
 Сообщения выводятся в stdout.  Если информационные сообщения отсутствуют, то либо код не содержит циклов, либо уровень отчетности не настроен для передачи отчетов о циклах, которые не удалось распараллелить.  Дополнительные сведения о кодах причин и сообщениях см. в разделе [Сообщения векторизатора и параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### Настройка параметра компилятора \/Qpar\-report в Visual Studio  
  
1.  В области **Обозреватель решений** откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В диалоговом окне **Страницы свойств** в разделе **С\/С\+\+** выберите **Командная строка**.  
  
3.  В поле **Дополнительные параметры** введите `/Qpar-report:1` или `/Qpar-report:2`.  
  
### Настройка параметра компилятора \/Qpar\-report программным способом  
  
-   Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры \/Q \(низкоуровневые операции\)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Параллельное программирование с помощью собственного кода](http://go.microsoft.com/fwlink/?LinkId=263662)