---
title: Неустранимая ошибка NMAKE U1001 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1001
dev_langs:
- C++
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4e465af5b4fa22c5f0ba5a9e01ebde0a7ee89e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068147"
---
# <a name="nmake-fatal-error-u1001"></a>Неустранимая ошибка NMAKE U1001

Синтаксическая ошибка: недопустимый символ «символ» в макросе

Данный символ отображается в макросе, но не является буквой, цифрой или символом подчеркивания.

Эта ошибка может быть вызвана отсутствует двоеточие в раскрытии макроса:

```
syntax error : illegal character '=' in macro
```