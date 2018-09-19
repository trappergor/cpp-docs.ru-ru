---
title: Ошибка компилятора C2097 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2da955f5382a1ebacdb507a69ed02627b11462e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021867"
---
# <a name="compiler-error-c2097"></a>Ошибка компилятора C2097

Недопустимая инициализация

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Инициализация переменной с помощью на Непостоянное значение.

1. Инициализация короткого адреса с длинный адрес.

1. Инициализации локальной структуры, объединения или массива с использованием неконстантного выражения, при компиляции с параметром **/Za**.

1. Инициализация с использованием выражения, содержащего оператор-запятую.

1. Инициализация с помощью выражения, не являющегося константным или символьные.