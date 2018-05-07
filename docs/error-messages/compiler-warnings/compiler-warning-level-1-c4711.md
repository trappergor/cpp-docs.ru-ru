---
title: Предупреждение (уровень 1) C4711 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4711
dev_langs:
- C++
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1faa8051ea2d167ae1386ef30ac54166c942aaf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4711"></a>Предупреждение компилятора (уровень 1) C4711
функция "функция" выбрана для подстановки  
  
 Компилятор выполнил подстановку кода указанной функции, несмотря на то, что он не был помечен для встраивания.  
  
 C4711 включается, если [/Ob2](../../build/reference/ob-inline-function-expansion.md) указано.  
  
 Встраивание выполняется на усмотрение компилятора. Это предупреждение носит информационный характер.  
  
 Это предупреждение отключено по умолчанию. Чтобы включить предупреждение, используйте [#pragma warning](../../preprocessor/warning.md). Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .