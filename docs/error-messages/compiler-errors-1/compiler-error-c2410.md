---
title: Ошибка компилятора C2410 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba4c2b57bcae062ccf811e33cf1deaea45f83737
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052456"
---
# <a name="compiler-error-c2410"></a>Ошибка компилятора C2410

«Идентификатор»: неоднозначное имя члена в «контекст»

Идентификатор является членом более чем одной структуры или объединения в этом контексте.

Используйте спецификатор структуры или объединения на операнд, который вызвал ошибку. Спецификатор структуры или объединения — это идентификатор типа `struct` или `union` ( `typedef` имени или переменной того же типа как структуры или объединения, на которую ссылается). Спецификатор должен быть левый операнд из первого оператора выбора члена (.) чтобы использовать операнд.