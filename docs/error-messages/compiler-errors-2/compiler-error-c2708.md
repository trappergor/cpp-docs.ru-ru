---
title: Ошибка компилятора C2708 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2708
dev_langs:
- C++
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d30b2e5c1856a604ae314316cd71d6acc00a7c74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2708"></a>Ошибка компилятора C2708
«Идентификатор»: длина фактических параметров в байтах отличается от предыдущего вызова или ссылки  
  
 Объект [__stdcall](../../cpp/stdcall.md) функции должен предшествовать прототип. В противном случае компилятор интерпретирует первый вызов функции как прототип, и эта ошибка возникает, когда компилятор обнаруживает вызов, который не совпадает.  
  
 Для исправления ошибки добавьте прототип функции.