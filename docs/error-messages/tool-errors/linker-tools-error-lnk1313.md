---
title: Ошибка средств компоновщика LNK1313 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1313
dev_langs:
- C++
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a896c8ba012c69755c5292475b2d155ad92066
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705092"
---
# <a name="linker-tools-error-lnk1313"></a>Ошибка средств компоновщика LNK1313

> обнаружен модуль ijw/native, невозможно скомпоновать с чистыми модулями

## <a name="remarks"></a>Примечания

Текущая версия Visual C++ не поддерживает связывание машинного или смешанного управляемого/неуправляемого OBJ-файлов с OBJ-файлы, скомпилированные с **/CLR: pure**.

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

## <a name="example"></a>Пример

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

## <a name="example"></a>Пример

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

## <a name="example"></a>Пример

Следующий пример кода образует ошибку LNK1313.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```