---
title: "Предупреждение (уровень 4) C4710 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4710
dev_langs: C++
helpviewer_keywords: C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0464d924c21a029a97a8f03d30f88127f3aea6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4710"></a>Предупреждение компилятора (уровень 4) C4710
«функция»: функция не является встроенной  
  
 Данная функция была выбрана для подстановки, но компилятор не выполняет встраивание.  
  
 Встраивание выполняется на усмотрение компилятора. **Встроенного** ключевое слово, таких как **зарегистрировать** используется ключевое слово, как указание для компилятора. Компилятор использует эвристику для определения должно подстановку определенной функции для ускорения код скорость компиляции, или должно подстановку определенной функции, чтобы сделать код более мелкие минимального объема. Компилятор выполняет только встроенные функции малого минимального объема.  
  
 В некоторых случаях компилятор выполняет встроенную определенных функций по техническим причинам. В разделе [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) список причин, по которым может быть встроенной функции.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .