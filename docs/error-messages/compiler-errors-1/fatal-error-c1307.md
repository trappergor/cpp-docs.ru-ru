---
title: "Неустранимая ошибка C1307 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1307"
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

программа была изменена после сбора данных о профилях  
  
 При использовании [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) компоновщик обнаружил модуль ввода, который был перекомпилирован после \/LTCG:PGINSTRUMENT, а также изменение модуля, при котором данные профиля более не являются значимыми.  Например, если в повторно компилированном модуле был изменен граф вызова, компилятор создает ошибку C1307.  
  
 Чтобы устранить данную ошибку, следует запустить \/LTCG:PGINSTRUMENT, повторно выполнить проверку и запустить \/LTCG:PGOPTIMIZE.  Если запуск \/LTCG:PGINSTRUMENT и повторное выполнение проверок невозможны, для создания оптимизированного образа следует использовать \/LTCG:PGUPDATE вместо \/LTCG:PGOPTIMIZE.