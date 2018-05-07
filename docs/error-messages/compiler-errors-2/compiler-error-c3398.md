---
title: Ошибка компилятора C3398 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b870479977bfb49ff39d5a15fe19fc700ed66b8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3398"></a>Ошибка компилятора C3398
"оператор": не удается преобразовать из "сигнатура_функции" в "указатель_функции". Исходное выражение должно являться символом функции  
  
 Когда соглашение о вызовах [__clrcall](../../cpp/clrcall.md) не указано, при компиляции с параметром **/clr**компилятор создает две точки входа (адреса) для каждой функции, основную точку входа и управляемую точку входа.  
  
 По умолчанию компилятор возвращает основную точку входа, но в некоторых случаях требуется управляемая точка входа (например, при назначении адреса указателю функции `__clrcall` ). Чтобы компилятор гарантированно выбрал управляемую точку входа в назначении, с правой стороны должен быть символ функции.