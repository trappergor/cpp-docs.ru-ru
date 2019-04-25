---
title: Неустранимая ошибка NMAKE U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 3b1df28e3cd7b27a9e7a130d9d71c1af68db9aec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324367"
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