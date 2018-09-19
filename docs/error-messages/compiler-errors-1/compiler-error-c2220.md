---
title: Ошибка компилятора C2220 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f4179b396e732ceeea20aeb9428d841a357a6d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051325"
---
# <a name="compiler-error-c2220"></a>Ошибка компилятора C2220

Предупреждение, обрабатываемое как ошибка - объектный файл не создан

[/WX](../../build/reference/compiler-option-warning-level.md) указывает компилятору обрабатывать все предупреждения как ошибки. Так как произошла ошибка, объект или исполняемый файл был создан.

Эта ошибка появляется, только когда **/WX** флага и возникновении предупреждения во время компиляции. Чтобы устранить эту ошибку, необходимо исключить каждого предупреждения в проекте.

### <a name="to-fix-use-one-of-the-following-techniques"></a>Чтобы устранить проблему, используйте один из следующих способов

- Устранение проблем, вызывающих предупреждения в проекте.

- Компиляция на более низком уровне предупреждение — например, использовать **/W3** вместо **/W4**.

- Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить или отключение определенных предупреждений.

- Не используйте **/WX** для компиляции.