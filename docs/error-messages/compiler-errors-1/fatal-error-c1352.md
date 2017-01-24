---
title: "Неустранимая ошибка C1352 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1352"
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Недопустимый или поврежденный блок MSIL в функции "функция" из модуля "файл"  
  
 Компилятору передан файл NETMODULE, но компилятор обнаружил поврежденный элемент файла.  Для получения сведений обратитесь к создателю файла NETMODULE.  
  
 Компилятор выполняет проверку наличия не всех типов повреждений в файлах NETMODULE.  Однако он проверяет все пути выполнения в функции на наличие оператора return.  
  
 Дополнительные сведения см. в разделе [NETMODULE\-файлы в качестве входных файлов компоновщика](../Topic/.netmodule%20Files%20as%20Linker%20Input.md).