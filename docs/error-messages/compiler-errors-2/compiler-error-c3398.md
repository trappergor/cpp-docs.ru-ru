---
title: "Ошибка компилятора C3398 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 66bd229369456da18d8bed60b25b6e6b07e03f27
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3398"></a>Ошибка компилятора C3398
"оператор": не удается преобразовать из "сигнатура_функции" в "указатель_функции". Исходное выражение должно являться символом функции  
  
 Когда [__clrcall](../../cpp/clrcall.md) соглашение о вызовах не указан при компиляции с параметром **/CLR**, компилятор создает две точки входа (адреса) для каждой функции, основную точку входа и управляемую точку входа.  
  
 По умолчанию компилятор возвращает основную точку входа, но в некоторых случаях требуется управляемая точка входа (например, при назначении адреса указателю функции `__clrcall` ). Чтобы компилятор гарантированно выбрал управляемую точку входа в назначении, с правой стороны должен быть символ функции.
