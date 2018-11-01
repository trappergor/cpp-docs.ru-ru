---
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: 77c60aed511fc3dbbea2d74e83e36dae735dcb0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578417"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

В результате вызова любого из потенциально небезопасных методов в стандартной библиотеке C++ [Предупреждение компилятора (уровень 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Чтобы отключить это предупреждение, определите _SCL_SECURE_NO_WARNINGS макрос в коде:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

При использовании предкомпилированных заголовков, поместите эту директиву в файл предкомпилированного заголовка до включения любой библиотеки времени выполнения C или заголовки стандартной библиотеки. Если поместить его в файле исходного кода перед включением предкомпилированного файла заголовка, он игнорируется компилятором.

## <a name="remarks"></a>Примечания

Другие способы отключения предупреждения C4996 перечислены ниже:

- Использование параметра компилятора [/D (определения препроцессора)](../build/reference/d-preprocessor-definitions.md):

   > CL myfile.cpp /D_SCL_SECURE_NO_WARNINGS [другие параметры компилятора]

- Использование параметра компилятора [/w](../build/reference/compiler-option-warning-level.md):

   > CL /wd4996 [другие параметры компилятора] myfile.cpp

- Использование директивы [предупреждение #pragma](../preprocessor/warning.md):

   ```cpp
   #pragma warning(disable:4996)
   ```

Кроме того, можно вручную изменить уровень предупреждения C4996 с параметром компилятора **/w\<l>\<n>**. Например, чтобы задать для предупреждения C4996 уровень 4:

> CL /w44996 [другие параметры компилятора] myfile.cpp

Дополнительные сведения см. в разделах [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>См. также

[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
