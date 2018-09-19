---
title: Предупреждение компилятора (уровень 4) C4718 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8736902f4c3a1cfac7313806fde65d1b253716b3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054237"
---
# <a name="compiler-warning-level-4-c4718"></a>Предупреждение компилятора (уровень 4) C4718

"вызов_функции": рекурсивный вызов не имеет побочных эффектов; удаление

Функция содержит рекурсивный вызов, но с другой стороны побочные эффекты отсутствуют. Вызов этой функции удаляется. Это повлияет на поведение программы, но не на ее правильность. В то время как оставленный вызов может привести к исключению переполнения стека, удаление этого вызова устраняет такую возможность.