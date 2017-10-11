---
title: "Ошибка компилятора C3398 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54241a6e57bdfd8795d6f894a1410c1e6c90cf49
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3398"></a>Ошибка компилятора C3398
"оператор": не удается преобразовать из "сигнатура_функции" в "указатель_функции". Исходное выражение должно являться символом функции  
  
 Когда соглашение о вызовах [__clrcall](../../cpp/clrcall.md) не указано, при компиляции с параметром **/clr**компилятор создает две точки входа (адреса) для каждой функции, основную точку входа и управляемую точку входа.  
  
 По умолчанию компилятор возвращает основную точку входа, но в некоторых случаях требуется управляемая точка входа (например, при назначении адреса указателю функции `__clrcall` ). Чтобы компилятор гарантированно выбрал управляемую точку входа в назначении, с правой стороны должен быть символ функции.
