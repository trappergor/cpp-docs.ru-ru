---
title: Ошибка компилятора C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: 30f472aa7a9475a19eea0e92fe5c2ea0d54e382b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209040"
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