---
title: Ошибка компилятора C2002 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b87a7fe1513c695344676624ae1968060097c885
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116923"
---
# <a name="compiler-error-c2002"></a>Ошибка компилятора C2002

Недопустимая константа Юникода

Недопустимая константа многобайтовых символов.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Расширенная символьная константа содержит большее число байтов, чем ожидалось.

1. Стандартный заголовок STDDEF.h не включается.

1. Расширенные символы не могут соединяться с обычными строковыми литералами.

1. Расширенная символьная константа должен предшествовать символ «L»:

    ```
    L'mbconst'
    ```

1. В Microsoft C++ текстовые аргументы директивы препроцессора должен быть ASCII. Например, директива `#pragma message(L"string")`, является недопустимым.