---
title: Неустранимая ошибка NMAKE U1100 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27ffd33a0a80056ee57f5f088823d7f8f6549c24
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135772"
---
# <a name="nmake-fatal-error-u1100"></a>Неустранимая ошибка NMAKE U1100

макрос «имя_макроса» является недопустимым в контексте пакетного правила «правило»

NMAKE создает эту ошибку, если блок команд правила пакетного режима прямо или косвенно ссылается на макрос специальный файл, который не является $<.

$< является единственным допустимым макрос для правила пакетного режима.