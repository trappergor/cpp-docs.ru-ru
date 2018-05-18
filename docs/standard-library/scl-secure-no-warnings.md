---
title: _SCL_SECURE_NO_WARNINGS | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec02ce5aab3d8a7f95ec9020fe3e2a00c1f5bef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

В результате вызова любого из потенциально небезопасных методов в стандартной библиотеке C++ [Предупреждение компилятора (уровень 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Чтобы отключить это предупреждение, определите в своем коде макрос **_SCL_SECURE_NO_WARNINGS**:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

При использовании предкомпилированных заголовков, прежде чем включать все библиотеки времени выполнения C, или заголовков стандартной библиотеки поместите этой директивы в файл предкомпилированного заголовка. Если поместить его в файле исходного кода перед включением файла предкомпилированного заголовка, он игнорируется компилятором.

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
