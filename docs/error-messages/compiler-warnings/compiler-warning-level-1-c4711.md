---
title: "Предупреждение (уровень 1) C4711 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4711
dev_langs: C++
helpviewer_keywords: C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9be609e0900ad5aea5011fbd880b7952e3e71cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4711"></a>Предупреждение компилятора (уровень 1) C4711
функция "функция" выбрана для подстановки  
  
 Компилятор выполнил подстановку кода указанной функции, несмотря на то, что он не был помечен для встраивания.  
  
 C4711 включается, если [/Ob2](../../build/reference/ob-inline-function-expansion.md) указано.  
  
 Встраивание выполняется на усмотрение компилятора. Это предупреждение носит информационный характер.  
  
 Это предупреждение отключено по умолчанию. Чтобы включить предупреждение, используйте [#pragma warning](../../preprocessor/warning.md). Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .