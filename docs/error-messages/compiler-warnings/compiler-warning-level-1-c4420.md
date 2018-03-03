---
title: "Предупреждение (уровень 1) C4420 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a57803cb584f5ee54ad5533366e6aadc85d1acf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4420"></a>Предупреждение компилятора (уровень 1) C4420
«оператор»: оператор недоступен, вместо этого использовать «оператор»; проверки во время выполнения могут выдать ошибку  
  
 Это предупреждение создается при использовании [правильной/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vector проверка) и если найдена ни одна форма вектор. В этом случае используется не векторная форма.  
  
 Для правильной работы правильно/RTCv компилятор должен всегда вызывать векторную форму [новый](../../cpp/new-operator-cpp.md)/[удалить](../../cpp/delete-operator-cpp.md) Если использовался синтаксис вектор.