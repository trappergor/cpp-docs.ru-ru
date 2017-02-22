---
title: "Предупреждение компилятора (уровень 1) C4420 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4420"
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор": оператор недоступен, вместо него используется "оператор"; проверки во время выполнения могут выдать ошибку  
  
 Это предупреждение создается при использовании [\/RTCv](../../build/reference/rtc-run-time-error-checks.md) \(проверка создания или удаления вектора\), и если не найдена векторная форма.  В этом случае используется не векторная форма.  
  
 Для правильной работы \/RTCv компилятор должен всегда вызывать векторную форму [создать](../../cpp/new-operator-cpp.md)\/[удалить](../../cpp/delete-operator-cpp.md), если использовался векторный синтаксис.