---
title: Предупреждение (уровень 1) C4420 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98336a30e7174b62df48e93a04ba9ee7ddcc919a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279114"
---
# <a name="compiler-warning-level-1-c4420"></a>Предупреждение компилятора (уровень 1) C4420
«оператор»: оператор недоступен, вместо этого использовать «оператор»; проверки во время выполнения могут выдать ошибку  
  
 Это предупреждение создается при использовании [правильной/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vector проверка) и если найдена ни одна форма вектор. В этом случае используется не векторная форма.  
  
 Для правильной работы правильно/RTCv компилятор должен всегда вызывать векторную форму [новый](../../cpp/new-operator-cpp.md)/[удалить](../../cpp/delete-operator-cpp.md) Если использовался синтаксис вектор.