---
title: Ошибка компилятора C2722
ms.date: 11/04/2016
f1_keywords:
- C2722
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
ms.openlocfilehash: 4274ac6ec33e0176f998fcf5a2b3efd570a4009f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546267"
---
# <a name="compiler-error-c2722"></a>Ошибка компилятора C2722

":: оператор": недопустимое обозначение оператора; Используйте оператор «оператор»

`operator` Переопределяет оператор `::new` или `::delete`. `new` И `delete` операторы являются глобальными, поэтому оператор разрешения области действия (`::`) не имеет смысла. Удалите оператор `::` .