---
title: Неустранимая ошибка NMAKE U1033 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7492e5fd77f8e88b2191174f84c298c6166d8d89
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066387"
---
# <a name="nmake-fatal-error-u1033"></a>Неустранимая ошибка NMAKE U1033

Синтаксическая ошибка: Непредвиденная «строка»

Строка, не входит в допустимый синтаксис файла makefile.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Если значение закрытия угловых скобок (**<<**) для встроенного файла не в начале строки, возникает следующая ошибка:

    ```
    syntax error : 'EOF' unexpected
    ```

1. Если определение макроса в файле makefile содержится знак равенства (**=**) без предшествующий имени или если имя определяемого представляет собой макрос, который пустой после подстановки, возникает следующая ошибка:

    ```
    syntax error : '=' unexpected
    ```

1. Если точка с запятой (**;**) в строке комментария в СРЕДСТВАХ. INI находится не в начале строки, возникает следующая ошибка:

    ```
    syntax error : ';' unexpected
    ```

1. Если файл makefile был отформатирован с помощью текстовых редакторов, может возникнуть следующая ошибка:

    ```
    syntax error : ':' unexpected
    ```