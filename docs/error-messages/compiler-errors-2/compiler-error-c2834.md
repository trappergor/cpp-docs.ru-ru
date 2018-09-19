---
title: Ошибка компилятора C2834 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b94e1a3fba9bc3589af020340651b4546347cf1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089350"
---
# <a name="compiler-error-c2834"></a>Ошибка компилятора C2834

«оператор» должен иметь глобальное полное имя

`new` И `delete` операторы привязаны к классу, где они находятся. Разрешение области не может использоваться для выбора версии `new` или `delete` от другого класса. Чтобы реализовать несколько форм `new` или `delete` оператор, создайте версию оператора с дополнительными формальными параметрами.